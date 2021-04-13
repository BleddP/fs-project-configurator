<template>
  <div class="flex-wrapper padding">
    <div class="container-center">
      <h3>Alle beschikbare oplossingen</h3>
      <!-- Check if there are any products that match search criteria -->
      <div>
        <h5 v-if="productsArray.length < 1">
          Sorry, we hebben geen geschikte opties voor je. Neem contact met ons
          op voor een tailor-made solution.
        </h5>
        <div v-else>
          <h5>
            We hebben {{ productsArray.length }} producten voor je gevonden:
          </h5>
          <div class="row">
            <div v-for="product in productsArray" :key="product.id">
              <div class="col-2">
                <product :product="product" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Product from './Product';

export default {
  name: 'ConfigResults',
  components: {
    Product,
  },
  props: {
    productsArray: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.product-card {
  margin: 10px;
  border: 1px solid gray;
}
</style>
