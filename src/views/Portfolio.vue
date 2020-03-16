<template>
  <div class="portfolio">
    <v-container>
      <v-row>
        <v-col class="pa-12" md="9">
          <h1 class="display-1 font-weight-bold pb-3">Projects</h1>
          <p
            class="headline"
            max-width="600px"
          >Below is a collection of work that I've had the opprotunity of being a part of. These range from sites i've been the solo developer on to being a part of a team that put together the whole.</p>
        </v-col>
      </v-row>
    </v-container>

    <v-layout>
      <v-container fluid>
        <v-row flex-wrap class="pa-2">
          <v-col v-bind:key="i" v-for="(item, i) in portfolioItems" md="4" sm="6" xs="12">
            <v-card class="portfolio-item">
              <v-img class="white--text" :src="item.img" height="250px">
                <div class="d-flex justify-space-between card-info">
                  <div class="pa-4 font-weight-bold title">{{item.title}}</div>
                  <v-btn
                    class="ma-4 pa-4 white black--text"
                    x-small
                    icon
                    target="_blank"
                    :href="item.link"
                  >
                    <v-icon>mdi-open-in-new</v-icon>
                  </v-btn>
                </div>
              </v-img>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-layout>
  </div>
</template>
<script>
export default {
  data: () => ({
    portfolioItems: [
      {
        title: "scannedMedia",
        link: "https://www.scanned.media",
        img: "https://cdn.vuetifyjs.com/images/cards/docks.jpg"
      },
      {
        title: "Crown Craft",
        link: "https://www.crowncraft.trade",
        img: "https://cdn.vuetifyjs.com/images/cards/docks.jpg"
      },
      {
        title: "scannedMedia",
        link: "https://www.scanned.media",
        img: "https://cdn.vuetifyjs.com/images/cards/docks.jpg"
      }
    ]
  })
};
</script>

<style lang="scss">
.portfolio-item {
  border-radius: 26px !important;
  .card-info {
    background-color: rgba(0, 0, 0, 0.6);
    overflow: hidden;
    // height: 0px;
    height: 0px;
    transition: all 0.3s ease-in-out;
  }
}
.portfolio-item:hover {
  .card-info {
    height: 66px;
  }
}
@media only screen and (max-width: 768px) {
  .card-info {
    height: 66px !important;
  }
}
</style>