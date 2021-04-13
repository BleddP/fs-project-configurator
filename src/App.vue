<template>
  <div id="app">
    <Home />
    <ConfiguratorView />
  </div>
</template>

<script>
import Home from "./views/Home";
import ConfiguratorView from "./views/ConfiguratorView";

export default {
  name: "App",
  components: {
    Home,
    ConfiguratorView
  }
};
</script>

<style>
@import "../src/styles/css/globals.css";
</style>
