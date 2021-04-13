<template>
  <div>
    <div class="steel-bg">
      <ConfigIntro />
      <ConfigQuestions
        :selectDoorType="selectDoorType"
        :selectAssembly="selectAssembly"
        :selectSelfHealing="selectSelfHealing"
        :selectStainlessSteel="selectStainlessSteel"
        :selectWindLoad="selectWindLoad"
        @select-width="selectWidth"
        @select-height="selectHeight"
      />
    </div>
    <ConfigResults :productsArray="productsArray" />
    <ConfigContact />
  </div>
</template>

<script>
import ConfigIntro from '../components/interactive/configurator/ConfigIntro';
import ConfigQuestions from '../components/interactive/configurator/ConfigQuestions';
import ConfigResults from '../components/interactive/configurator/ConfigResults';
import ConfigContact from '../components/interactive/configurator/ConfigContact';
import axios from 'axios';
// import products from "../../public/test_data/products.json";

export default {
  name: 'ConfiguratorView',
  components: {
    ConfigIntro,
    ConfigQuestions,
    ConfigResults,
    ConfigContact,
  },
  data() {
    return {
      products: [],
      productsArray: [],
      selectors: {
        type: 'A',
        width: 2000,
        height: 2000,
        assemblyPosition: 'left',
        selfHealing: true,
        stainlessSteel: true,
        windLoad: 4,
      },
    };
  },
  methods: {
    selectDoorType(value) {
      // const setFilter = this.products.filter((door) => door.type === value);
      console.log('Door Type:', value);
      this.selectors.type = value;
      filterResults(this);
    },
    selectWidth(value) {
      // this.productsArray = this.products.filter((door) => door.width < value);
      console.log('Width: ', value);
      this.selectors.width = value;
    },
    selectHeight(value) {
      // this.productsArray = this.products.filter((door) => door.height < value);
      console.log('Height: ', value);
      this.selectors.height = value;
    },
    selectAssembly(value) {
      // this.productsArray = this.products.filter(
      //   (door) => door.assemblyPosition === value
      // );
      console.log('Assemby: ', value);
      this.selectors.assemblyPosition = value;
    },
    selectSelfHealing(value) {
      // this.productsArray = this.products.filter(
      //   (door) => door.selfHealing === value
      // );
      console.log('Self Healing??', value);
      this.selectors.selfHealing = value;
    },
    selectStainlessSteel(value) {
      // this.productsArray = this.products.filter(
      //   (door) => door.stainlessSteel === value
      // );
      console.log('RVS???', value);
      this.selectors.stainlessSteel = value;
    },
    selectWindLoad(value) {
      // this.productsArray = this.products.filter(
      //   (door) => door.windLoad === value
      // );
      console.log(('Wind Load: ', value));
      this.selectors.windload = value;
    },
  },
  // Get the initial data from a JSON file
  created() {
    axios
      .get('/test_data/products.json')
      .then((res) => {
        this.products = res.data.doorTypes;
        this.productsArray = res.data.doorTypes;
      })
      .catch((err) => {
        console.log({ err });
      });
  },
};

const filterResults = (current) => {
  current.productsArray = current.products.filter((door) => {
    door.type === current.selectors.type &&
      door.width < current.selectors.width &&
      door.height < current.selectors.height &&
      door.assemblyPosition === current.selectors.assemblyPosition &&
      door.selfHealing === current.selectors.selfHealing &&
      door.stainlessSteel === current.selectors.stainlessSteel &&
      door.windload === current.selectors.windload;
  });
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
