<template>
  <div id="app">
    <GridPage msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import GridPage from "./components/GridPage.vue";

export default {
  name: "App",
  components: {
    GridPage,
  },
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  font-family: "Roboto", sans-serif;
}
body {
  margin: 0;
}
.d-flex {
  display: flex;
  flex-wrap: wrap;
}
.text-center {
  text-align: center;
}
#app {
  width: 100%;
  max-width: 960px;
  margin: 0 auto;
}
</style>
