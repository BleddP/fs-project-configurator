<template>
  <div class="product-card">
    <div class="flex">
      <img
        src="https://www.pngkey.com/png/detail/338-3381684_garage-door.png"
        alt="Door"
        width="100%"
      />
    </div>
    <div class="description">
      <h5>{{ product.name }}</h5>
      <p>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Voluptatum
        officiis quos perspiciatis dolores dignissimos mollitia cum, nisi magnam
        placeat nihil!
      </p>
    </div>
    <div class="row">
      <div class="col-4 flex-center-all ">
        <h4 class="orange-text ">Meer Informatie</h4>
      </div>
      <div class="col-2 flex-center-all orange-bg">
        <h4>Arrow</h4>
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
</style>
