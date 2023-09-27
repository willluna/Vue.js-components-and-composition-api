<template>
  <HomeVue name="Will" last-name="Luna"></HomeVue>
  <HomeOptions name="Will" last-name="Luna"></HomeOptions>
</template>

<script>
import HomeVue from "./components/HomeVue.vue";
import { provide } from "vue";
import HomeOptions from "./components/HomeOptions.vue";

export default {
  name: "App",
  components: {
    HomeVue,
    HomeOptions,
  },
  setup() {
    provide("userName", "WillPlayer");
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
