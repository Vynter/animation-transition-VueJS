<template>
  <div id="app" class="container">
    <transition name="qqq" appear appear-class="qqq">
      <img alt="Vue logo" src="./assets/logo.png" />
      <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    </transition>
    <Alertz></Alertz>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Alertz from "./components/Alert.vue";
export default {
  name: "App",
  components: {
    // HelloWorld,
    Alertz,
  },
};
</script>

<style>
  #app {
   font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

} 

.qqq-enter-actove,
.qqq-leave-active {
  transition: all 1s;
}

.qqq-enter,
.qqq-leave-active {
  opacity: 0;
  transform: translateX(20px);
}
</style>
