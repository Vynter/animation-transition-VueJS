<template>
  <div id="random">
    <transition name="fade" mode="out-in">
      <!--mode="in-out"-->
      <div class="ui message success" v-if="dispo" key="visible">
        <p>show content</p>
      </div>
      <div class="ui message success" v-else key="invisible">
        <p>and now V else</p>
      </div>
    </transition>
    <hr />
    <transition :css="false" @enter="enter" @leave="leave">
      <div class="ui message success" v-if="dispo">
        <p>2eme animation</p>
      </div>
    </transition>
    <button v-on:click="toggle">Active</button>
    <!--  -->
    <transition-group name="bounce" tag="ul" appear="">
      <li v-for="(item, index) in items" :key="index">{{ item }}</li>
    </transition-group>
    <!--  -->
    <button type="button" class="btn btn-outline-primary" v-on:click="add">
      Display
    </button>
    <button type="button" class="btn btn-outline-danger" v-on:click="melange">
      error
    </button>
  </div>
</template>

<script>
import $ from "jquery";
export default {
  name: "Alertz",
  data() {
    return {
      dispo: true,
      items: [101, 102, 103, 104, 105],
    };
  },
  methods: {
    add: function() {
      this.items.push(Math.random());
    },
    melange: function() {
      this.items = [104, 101, 105, 103, 102];
      // this.items.reverse();
    },
    //
    //
    enter: function(el, done) {
      $(el) // utilisation de jquery
        .hide()
        .slideDown(500, done);
      console.log("ok");
    },
    leave: function(el, done) {
      $(el)
        .show()
        .slideUp(500, done);
    },
    toggle: function() {
      this.dispo = !this.dispo;
    },
  },
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s, transform 1s;
}
.fade-enter,
.fade-leave-active {
  opacity: 0;
  transform: translateX(20px);
}

.fade-move {
  transition: 1s;
}

.fade2-enter-active,
.fade2-leave-active {
  transition: opacity 0.5s, transform 1s;
}
.fade2-enter,
.fade2-leave-active {
  opacity: 0;
  transform: translate(30px, 20px);
}

.fade2-move {
  transition: transform 10s;
}
/* bounce */
.bounce-enter-active {
  animation: bounce-in 0.5s;
}
.bounce-leave-active {
  animation: bounce-in 0.5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
.bounce-move {
  transition: transform 1s;
  transform: translateY(-120px);
}
</style>
