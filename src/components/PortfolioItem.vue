<template>
  <v-card class="portfolio-item">
    <v-toolbar
      desnity="compact"
      height="48"
      elevation="6"
      color="grey-lighten-3"
    >
      <v-card-actions class="pl-4">
        <v-icon color="red-lighten-1" icon="mdi-circle" size="small" />
        <v-icon color="yellow-darken-3" icon="mdi-circle" size="small" />
        <v-icon color="green-lighten-1" icon="mdi-circle" size="small" />
      </v-card-actions>
      <p v-if="location == home" class="text-grey">
        {{ link }}
      </p>
      <v-spacer />
      <v-btn small icon target="_blank" :href="link">
        <v-icon color="222" icon="mdi-open-in-new" />
      </v-btn>
    </v-toolbar>

    <v-img
      :src="image"
      lazy-src="https://loremflickr.com/160/90/cat"
      aspect-ratio="16 / 9"
      min-height="190"
    >
      <template #placeholder>
        <div class="d-flex align-center justify-center fill-height">
          <v-progress-circular color="grey-lighten-4" indeterminate />
        </div>
      </template>
    </v-img>

    <div v-if="location != home">
      <v-card-title class="pt-3 pb-4 body-2 text-capitalized font-weight-bold">
        {{ title }}
      </v-card-title>
      <v-card-text>
        <v-row class="pa-3 pt-2 pb-4">
          <div v-for="(tool, x) in tools" :key="tool" class="pr-2">
            <v-chip
              v-if="x == 0"
              color="indigo-darken-4"
              class="font-weight-bold"
              :text="tool"
            />
            <v-chip v-else color="cyan-darken-4" :text="tool" />
          </div>
        </v-row>
      </v-card-text>
    </div>

    <!-- <v-card-text class="text--primary pt-0 pb-5">
                <div>Whitsunday Island, Whitsunday Islands</div>
              </v-card-text> -->
  </v-card>
</template>

<script setup>
defineProps({
  title: String,
  link: String,
  image: String,
  tools: Array,
  location: String,
});
// ...
</script>

<style lang="scss">
.portfolio-item {
  border-radius: 15px !important;
}
</style>
