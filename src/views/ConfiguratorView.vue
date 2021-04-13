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
import ConfigIntro from "../components/interactive/configurator/ConfigIntro";
import ConfigQuestions from "../components/interactive/configurator/ConfigQuestions";
import ConfigResults from "../components/interactive/configurator/ConfigResults";
import ConfigContact from "../components/interactive/configurator/ConfigContact";
import axios from "axios";

export default {
  name: "ConfiguratorView",
  components: {
    ConfigIntro,
    ConfigQuestions,
    ConfigResults,
    ConfigContact
  },
  data() {
    return {
      products: [],
      productsArray: [],
      type: null,
      width: 0,
      height: 0,
      assemblyPosition: null,
      selfHealing: null,
      stainlessSteel: null,
      windLoad: null
    };
  },
  methods: {
    selectDoorType(value) {
      this.type = value;
      this.productsArray = filterResults(this);
    },
    selectWidth(value) {
      this.width = value;
      this.productsArray = filterResults(this);
    },
    selectHeight(value) {
      this.height = value;
      this.productsArray = filterResults(this);
    },
    selectAssembly(value) {
      this.assemblyPosition = value;
      this.productsArray = filterResults(this);
    },
    selectSelfHealing(value) {
      this.selfHealing = value;
      this.productsArray = filterResults(this);
    },
    selectStainlessSteel(value) {
      this.stainlessSteel = value;
      this.productsArray = filterResults(this);
    },
    selectWindLoad(value) {
      this.windLoad = value;
      this.productsArray = filterResults(this);
    }
  },

  // Get the initial data from a JSON file
  created() {
    axios
      .get("/test_data/products.json")
      .then(res => {
        this.products = res.data.doorTypes;
        this.productsArray = res.data.doorTypes;
      })
      .catch(err => {
        console.log({ err });
      });
  }
};

function filterResults(input) {
  const filteredResults = input.products.filter(door => {
    return (
      (input.type === door.type || !input.type) &&
      (input.width < door.width ?? input.type === 0) &&
      (input.height < door.height ?? input.type === 0) &&
      (input.assemblyPosition === door.assemblyPosition ||
        !input.assemblyPosition) &&
      (input.selfHealing === door.selfHealing || !input.selfHealing) &&
      (input.stainlessSteel === door.stainlessSteel || !input.stainlessSteel) &&
      (input.windLoad === door.windLoad || !input.windLoad)
    );
  });
  return filteredResults;
}
</script>

<style scoped></style>
