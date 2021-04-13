<template>
  <div class="row black-bg">
    <div class="col-5 flex">
      <ul class="menu-items">
        <li>Home</li>
        <li>Configurator</li>
        <li>Industriedeuren</li>
        <li>Spare Parts</li>
        <li>Garagedeuren</li>
        <li>Overige</li>
      </ul>
    </div>
    <div class="col-1">Search</div>
  </div>
</template>

<script>
export default {
  name: "Configurators"
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
  width: 100%;
  height: 100px;
  color: #fff;
  display: flex;
  align-items: center;
  padding-left: 50px;
}

li {
  display: inline-block;
  *display: inline;
  padding-left: 25px;
}
</style>
