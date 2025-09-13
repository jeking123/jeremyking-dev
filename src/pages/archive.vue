<template>
  <div class="portfolio mb-10">
    <v-container>
      <v-row>
        <v-col>
          <h1 class="display-1 font-weight-bold pb-1">All Projects</h1>
          <!-- <p class="headline" style="max-width: 600px">
            List of past projects and work.
          </p> -->
        </v-col>
      </v-row>
    </v-container>
    <PortfolioItems location="archive" />
  </div>
</template>

<script>
import PortfolioItems from "../components/PortfolioItems";

// defineProps({
//   data: Array,
// });

export default {
  data: () => ({}),
};
</script>

<style lang="scss">
// . . .
</style>
