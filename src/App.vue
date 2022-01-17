<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Main,
    Header,
  },
};
</script>

<style lang="scss">
  @import "./assets/scss/style.scss";
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap');
</style>
