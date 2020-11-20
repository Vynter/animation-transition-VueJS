<template>
  <div id="app" class="container">
    <transition name="qqq" appear>
      <div  v-if="okk">
        <img alt="Vue logo" src="./assets/logo.png" />
        <p>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Mollitia
          magni vel a laudantium aperiam sunt quam officia expedita. Nemo
          doloremque iste a magni minus ab animi amet perspiciatis expedita
          eaque?
        </p>
      </div>
      <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    </transition>
    <button @click="okk = !okk">tog</button>
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
  data() {
    return {
      okk: true,
    };
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

.qqq-enter-active,
.qqq-leave-active {
  transition: all 1s;
}
.qqq-leave {
  transform: translateX(20px);
}
.qqq-enter,
.qqq-leave-active {
  opacity: 0;
  transform: translateX(20px);
}

.qqq-move {
  transition: transform 1s;
  transform: translateY(-120px);
}
</style>
