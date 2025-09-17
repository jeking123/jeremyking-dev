<template>
  <div class="portfolio mb-10">
    <v-container>
      <v-row>
        <v-col>
          <h1 class="display-1 font-weight-bold pb-3">Design</h1>
          <p class="headline" style="max-width: 600px">
            Here’s a selection of my past design work, showcasing projects that
            balance visual appeal with practical functionality.
          </p>
        </v-col>
      </v-row>
    </v-container>
    <PortfolioItems location="design" />
    <v-row justify="center" class="mt-6 mb-4">
      <v-col cols="auto">
        <v-btn to="/archive" variant="tonal">View All Work</v-btn>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import PortfolioItems from "../components/PortfolioItem";

export default {
  components: {
    PortfolioItems,
  },
  data: () => ({}),
};
</script>

<style lang="scss">
.featuredText {
  width: 750px;
}
@media only screen and (max-width: 768px) {
  .card-info {
    height: 66px !important;
  }
  .featuredText {
    width: 80%;
  }
}
</style>
