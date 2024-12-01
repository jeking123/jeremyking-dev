<template>
  <v-footer class="pa-0 d-flex flex-column">
    <div class="bg-teal d-flex w-100 align-center pa-5">
      <v-container>
        <v-row>
          <strong>Made with Vue & Vuetify</strong>

          <v-spacer />

          <div class="d-flex ga-1 align-content-center">
            <v-icon icon="mdi-copyright" />
            <p>{{ new Date().getFullYear() }} <strong>Jeremy King</strong></p>
          </div>
        </v-row>
      </v-container>
    </div>
  </v-footer>
</template>
