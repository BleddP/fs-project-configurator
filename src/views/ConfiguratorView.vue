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
      type: '',
      width: 5000,
      height: 5000,
      assemblyPosition: '',
      selfHealing: null,
      stainlessSteel: null,
      windLoad: null,
    };
  },
  methods: {
    selectDoorType(value) {
      this.type = value;
      this.filterResults();
    },
    selectWidth(value) {
      this.width = value;
      this.filterResults();
    },
    selectHeight(value) {
      this.height = value;
      this.filterResults();
    },
    selectAssembly(value) {
      this.assemblyPosition = value;
      this.filterResults();
    },
    selectSelfHealing(value) {
      this.selfHealing = value;
      this.filterResults();
    },
    selectStainlessSteel(value) {
      this.stainlessSteel = value;
      this.filterResults();
    },
    selectWindLoad(value) {
      this.windLoad = value;
      this.filterResults();
    },
    filterResults() {
      const {
        type,
        width,
        height,
        assemblyPosition,
        selfHealing,
        stainlessSteel,
        windLoad,
      } = this;

      /// Filter the room by door type
      let byDoorType;
      if (type !== '') {
        byDoorType = this.products.filter((door) => door.type === type);
      } else {
        byDoorType = this.products;
      }

      /// Filter the door by width
      const byWidth = byDoorType.filter((door) => width < door.width);

      /// Filter the door by height
      const byHeight = byWidth.filter((door) => height < door.height);

      /// Filter the door by assembly left/right
      let byAssemblyPosition;
      if (assemblyPosition !== '') {
        byAssemblyPosition = byHeight.filter(
          (door) => door.assemblyPosition === assemblyPosition
        );
      } else {
        byAssemblyPosition = byHeight;
      }

      /// Filter the door by self-healing properties
      let bySelfHealing;
      if (selfHealing !== null) {
        bySelfHealing = byAssemblyPosition.filter(
          (door) => door.selfHealing === selfHealing
        );
      } else {
        bySelfHealing = byAssemblyPosition;
      }

      /// Filter the door by stainless-steel
      let byStainlessSteel;
      if (stainlessSteel !== null) {
        byStainlessSteel = bySelfHealing.filter(
          (door) => door.stainlessSteel === stainlessSteel
        );
      } else {
        byStainlessSteel = bySelfHealing;
      }

      /// Filter the door by windload
      let byWindLoad;
      if (windLoad !== 0) {
        byWindLoad = byStainlessSteel.filter(
          (door) => door.windLoad === windLoad
        );
      } else {
        byWindLoad = byStainlessSteel;
      }

      const filteredResults = byWindLoad;
      return (this.productsArray = filteredResults);
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
</script>

<style scoped></style>
