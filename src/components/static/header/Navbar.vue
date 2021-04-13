<template>
  <div class="row orange-bg">
    <div class="col-5">
      <ul class="menu-items">
        <li>Over Alpha Deuren</li>
        <li>Projecten</li>
        <li>Vacatures</li>
        <li>Downloads</li>
        <li>Dealer worden</li>
        <li>Contact</li>
      </ul>
    </div>
    <div class="col-1">
      [FLAG]
      <strong>NL</strong>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  margin: 0px;
  padding: 0px;
}

.orange-bg {
  background: orange;
  height: 50px;
  display: flex;
  align-items: center;
  padding-left: 50px;
}

li {
  display: inline-block;
  *display: inline;
  padding-left: 10px;
}
</style>
