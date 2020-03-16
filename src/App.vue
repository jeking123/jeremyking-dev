<template>
  <v-app>
    <Navigation />
    <transition name="slide-fade" mode="out-in">
      <router-view></router-view>
    </transition>
  </v-app>
</template>

<script>
import Navigation from "./components/Navigation.vue";
export default {
  name: "App",
  components: {
    Navigation
  },
  data: () => ({})
};
</script>

<style lang="scss">
.body {
  overflow: hidden;
}
/* Enter and leave animations can use different */
/* durations and timing functions.              */
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.4s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
</style>
