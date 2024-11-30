<template>
  <div>
    <v-navigation-drawer v-model="drawer" app width="300px">
      <h3 block class="text-center pt-5 pb-10">Jeremy King</h3>
      <v-spacer></v-spacer>
      <div class="d-flex justify-center pb-8">
        <v-img
          alt="jeremy"
          src="../assets/Jeremy-avatar-2.png"
          max-width="150"
        />
      </div>
      <v-spacer></v-spacer>
      <v-btn block text to="/" @click="drawer = false">home</v-btn>
      <v-btn block text to="/portfolio" @click="drawer = false"
        >portfolio</v-btn
      >
      <v-btn block text to="/resume" @click="drawer = false">resume</v-btn>
      <v-spacer></v-spacer>
      <v-list disabled>
        <!-- <v-subheader>info</v-subheader> -->
        <v-list-item :key="i" v-for="(item, i) in info">
          <v-list-icon>
            <v-icon v-text="item.icon" class="px-3"></v-icon>
          </v-list-icon>
          <v-list-content>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-container fluid>
      <v-toolbar flat app>
        <v-toolbar-title class="d-flex align-center">
          <a href="/">
            <img src="../assets/logo.svg" width="40px" />
          </a>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-side-icon>
          <v-btn icon @click="drawer = !drawer">
            <v-icon v-if="!drawer">mdi-menu</v-icon>
            <v-icon v-else>mdi-close</v-icon>
          </v-btn>
        </v-toolbar-side-icon>
      </v-toolbar>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    info: [
      {
        icon: "mdi-email",
        text: "me@jeremyking.dev",
      },
      {
        icon: "mdi-github",
        text: "jeking123",
      },
      {
        icon: "mdi-copyright",
        text: "Jeremy King 2024",
      },
      {
        icon: "",
        text: "Made with Vue and Vuetify",
      },
    ],
  }),
};
</script>

<style lang="scss">
.background {
  overflow: hidden;
}
.v-navigation-drawer__content {
  display: flex;
  flex-direction: column;
}
</style>
