<template>
  <div>
    <div class="steel-bg">
      <ConfigIntro />
      <ConfigQuestions />
    </div>
    <ConfigResults />
    <ConfigContact />
    <button>Click me</button>
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
    };
  },
  methods: {},
  created() {
    axios
      .get('/test_data/products.json')
      .then((res) => {
        self.products = res.data.doorTypes;
      })
      .catch((err) => {
        console.log({ err });
      });
  },
};

// function getData() {
//   axios
//     .get('/test_data/products.json')
//     .then((res) => {
//       console.log(res.data.doorTypes);
//       self.products = res.data.doorTypes;
//     })
//     .catch((err) => {
//       console.log({ err });
//     });
//   // const res = await fetch("/test_data/products.json");
//   // const result = res.json();
//   // console.log(result);
//   // .then(res => {
//   //   res.json();
//   // })
//   // .then(response => {
//   //   console.log("DOOR TYPES: ", response);
//   //   this.products = [];
//   // });
// }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
