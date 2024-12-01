<template>
  <v-app>
    <Navigation />
    <v-main>
      <router-view />
      <Footer />
    </v-main>
  </v-app>
</template>

<script setup>
import Navigation from "./components/Navigation.vue";
import Footer from "./components/Footer.vue";
</script>
