<template>
  <div id="app">
    <ActiveBoot />
    <img alt="Vue logo" src="./assets/co2.jpg" />
    <HelloWorld msg="Welcome to Carbon Emission Intensity App" />
    <regionList />
    
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import regionList from "./components/regionList.vue";
import ActiveBoot from './components/ActiveBoot.vue';
export default {
  name: "App",
  components: {
    HelloWorld,
    regionList,
    ActiveBoot,
  },
};
</script>

<style lang="scss">
@import "~@/assets/scss/vendors/bootstrap-vue/index";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
