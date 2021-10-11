<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/co2.jpg" />
    <HelloWorld msg="Welcome to Carbon Emission Intensity App" />
    <regionList />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import regionList from "./components/regionList.vue";
export default {
  name: "App",
  components: {
    HelloWorld,
    regionList
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
