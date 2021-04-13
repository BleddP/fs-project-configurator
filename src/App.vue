<template>
  <div id="app">
    <Header />
    <Home />
    <Footer />
  </div>
</template>

<script>
import Home from './views/Home';
import Header from './components/static/header/Header';
import Footer from './components/static/Footer';

export default {
  name: 'App',
  components: {
    Home,
    Header,
    Footer,
  },
};
</script>

<style>
@import '../src/styles/css/globals.css';
</style>
