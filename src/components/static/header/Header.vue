<template>
  <div class="header-container">
    <div class="container">
      <div class="row">
        <div class="col-1">
          <div class="logo">
            <h1>Logo</h1>
          </div>
        </div>
        <div class="col-5">
          <div>
            <Navbar />
          </div>
          <div>
            <Configurators />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "./Navbar";
import Configurators from "./Configurators";

export default {
  name: "Header",
  components: {
    Navbar,
    Configurators
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header-container {
  height: 100px;
}

.logo {
  background: red;
  height: 150px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
