<template>
  <div>
    <v-toolbar
      flat
      color="white"
      class="pa-5"
    >
      <v-container>
        <v-row>
          <v-toolbar-title class="d-flex align-center">
            <a href="/">
              <img
                src="../assets/logo.svg"
                width="40px"
              >
            </a>
          </v-toolbar-title>
          <v-spacer />
          <v-btn
            icon
            @click.stop="drawer = !drawer"
          >
            <v-icon v-if="!drawer">
              mdi-menu
            </v-icon>
            <v-icon v-else>
              mdi-close
            </v-icon>
          </v-btn>
        </v-row>
      </v-container>
    </v-toolbar>

    <v-navigation-drawer
      v-model="drawer"
      temporary
    >
      <h3
        block
        class="text-center pt-5 pb-10"
      >
        Jeremy King
      </h3>
      <v-spacer />
      <div class="d-flex justify-center pb-8">
        <v-img
          alt="jeremy king"
          src="../assets/Jeremy-avatar-2.png"
          max-width="150"
        />
      </div>
      <v-spacer />
      <v-btn
        block
        text
        to="/"
        @click="drawer = false"
      >
        home
      </v-btn>
      <v-btn
        block
        text
        to="/portfolio"
        @click="drawer = false"
      >
        portfolio
      </v-btn>
      <v-btn
        block
        text
        to="/resume"
        @click="drawer = false"
      >
        resume
      </v-btn>
      <v-spacer />
      <v-list
        disabled
        :items="items"
      />
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    group: null,
    items: [
      {
        title: "me@jeremyking.dev",
        value: 1,
        props: {
          prependIcon: "mdi-email",
        },
      },
      {
        title: "jeking123",
        value: 2,
        props: {
          prependIcon: "mdi-github",
        },
      },
      // {
      //   title: "Jeremy King 2024",
      //   value: 3,
      //   props: {
      //     prependIcon: "mdi-copyright",
      //   },
      // },
      // {
      //   title: "Made with Vue and Vuetify",
      //   value: 4,
      //   props: {
      //     prependIcon: "",
      //   },
      // },
    ],
  }),
  watch: {
    group() {
      this.drawer = false;
    },
  },
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
