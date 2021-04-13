<template>
  <div class="header-container">
    <div class="container">
      <div class="row">
        <div class="col-1">
          <div class="flex-center-all mobile-disappear">
            <img src="../../../assets/logo.png" alt="logo" height="100%" />
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
import Navbar from './Navbar';
import Configurators from './Configurators';

export default {
  name: 'Header',
  components: {
    Navbar,
    Configurators,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
