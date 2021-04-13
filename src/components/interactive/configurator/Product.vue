<template>
  <div class="product-card">
    <div class="flex">
      <img :src="product.productImage" :alt="product.name" class="image" />
    </div>
    <div class="description">
      <h3>{{ product.name }}</h3>
      <p>
        {{ product.descriptionShort }}
      </p>
      <h5>Beschikbare kleuren:</h5>
      <span class="colours" v-for="color in product.colors" :key="color">
        {{ color }},
      </span>
    </div>
    <div class="row">
      <div class="col-4 flex-center-all link">
        <h4 class="orange-text ">Meer Informatie</h4>
      </div>
      <div class="col-2 flex-center-all orange-bg">
        <h4>
          <img
            src="https://www.pngkit.com/png/full/79-790228_open-next-icon-white-png.png"
            alt=""
            height="20px"
          />
        </h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Product',
  props: {
    product: Object,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.product-card {
  margin: 10px;
  border: 1px solid gray;
}

.flex {
  display: flex;
  justify-content: center;
  align-items: center;
}

.description {
  border-top: 1px solid gray;
  padding: 20px;
}

.image {
  width: 100%;
  height: 250px;
}

.colours {
  padding: 0px;
  margin: 0px;
}
</style>
