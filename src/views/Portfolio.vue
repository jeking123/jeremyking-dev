<template>
  <div class="portfolio">
    <v-container>
      <v-row>
        <v-col>
          <h1 class="display-1 font-weight-bold pb-3">Projects</h1>
          <p
            class="headline"
            max-width="600px"
          >Below is a collection of work that I've done for myself or had the opportunity of being a part of.</p>
        </v-col>
      </v-row>
    </v-container>

    <v-layout>
      <v-container>
        <v-row flex-wrap class="pa-s">
          <v-col xs="12">
            <v-card style="border-radius: 26px;" elevation="4">
              <v-row>
                <v-col class="col-1">
                  <v-btn
                    class="pa-6 ml-6 mt-2 black white--text"
                    icon
                    target="_blank"
                    :href="featured.link"
                  >
                    <v-icon>mdi-open-in-new</v-icon>
                  </v-btn> 
                </v-col>
                <v-col class="col-11">
                <v-card-title class="pa-0 pt-1" width="100%">
                  {{featured.title}}
                </v-card-title> 
                <div>{{featured.subtext}}</div>
                </v-col>
              </v-row>
              
              <div class="pl-4 pb-3 featuredText">
                <v-text>Mobius is a non profit organization that focuses on providing educational and exciting content for kids and people of all ages. The goal of this website was to provide Mobius with a professional and easy to navigate website. That would showcase who they are. We also implemented an ordering system for Virutal Programs and Steam Kits, which are at home experiments kids can do while the center is closed due to covid 19. </v-text>
              </div>
              <v-img :src="featured.img" />
            </v-card>
          </v-col>
        </v-row>
        <v-row flex-wrap>
          <v-col :key="i" v-for="(item, i) in portfolioItems" md="4" sm="6" xs="12">
            <v-card class="portfolio-item">
              <v-img class="white--text" :src="item.img" height="350px">
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
import scannedMedia from "../assets/portfolio/scannedmedia.jpg";
import flootie from "../assets/portfolio/flootie.jpg";
import crowncraft from "../assets/portfolio/crowncraft.jpg";
import idlekingdoms from "../assets/portfolio/idle-kingdoms.jpg";
// import desertjewels from "../assets/portfolio/desertjewelsnursery.jpg";
import quotes from "../assets/portfolio/quote-deck.jpg";
import mobius from "../assets/portfolio/MobiusFeature.jpg";
export default {
  data: () => ({
    featured:{
      title: "Mobius Discovery Center",
      subtext: "Website Design & Development",
      link: "https://www.mobiusdiscoverycenter.org",
      img: mobius
    },
    portfolioItems: [
      {
        title: "Scanned Media",
        link: "https://www.scanned.media",
        img: scannedMedia
      },
      {
        title: "Crown Craft",
        link: "https://www.crowncraft.trade",
        img: crowncraft
      },
      {
        title: "Flootie",
        link: "https://www.flootie.com",
        img: flootie
      },
      {
        title: "Idle Kingdoms",
        link: "https://www.thinkingdesign.studio/portfolio/2018-idle-kingdoms/",
        img: idlekingdoms
      },
      //{
        //title: "Desert Jewels Nursery",
        //link: "https://www.desertjewelsnursery.com/",
        //img: desertjewels
      //},
      {
        title: "Quote Deck",
        link: "https://www.thinkingdesign.studio/portfolio/2016-Quote-Deck/",
        img: quotes
      }
    ]
  })
};
</script>

<style lang="scss">

.featuredText {
  width: 750px;
}
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
  .featuredText {
  width: 80%;
}
}
</style>
