<template>
  <div class="row black-bg">
    <div class="col-5 flex">
      <ul class="menu-items">
        <li class="active">Home</li>
        <li>Configurator</li>
        <li>Industriedeuren</li>
        <li>Spare Parts</li>
        <li>Garagedeuren</li>
        <li>Overige</li>
      </ul>
    </div>
    <div class="col-1 mobile-disappear">
      <img
        src="https://lh3.googleusercontent.com/proxy/2M24-qxUjaReei49Eez_RG2uhXaLBZICxVpX2NwUh6nk6ylLFoV0T7lzjke3wpAE-XjOnZqP4Ojkmh6mupTpo6Cps6RiL9LFurGwyg"
        width="30px"
        alt=""
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Configurators',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  margin: 0px;
  padding: 0px;
}
.black-bg {
  background-color: black;
  height: 100%;
  min-height: 100px;
  color: #fff;
  display: flex;
  align-items: center;
  padding-left: 50px;
  padding-top: 20px;
  padding-bottom: 20px;
}
</style>
