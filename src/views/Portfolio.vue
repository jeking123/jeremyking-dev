<template>
  <div class="portfolio">
    <v-container>
      <v-row>
        <v-col>
          <h1 class="display-1 font-weight-bold pb-3">Projects</h1>
          <p class="headline" max-width="600px">
            From WordPress & Shopify to Vue or React, I have experience building
            and launching high performing client projects. Below is a sample of
            client & personal work from over the years.
          </p>
        </v-col>
      </v-row>
    </v-container>

    <v-layout>
      <v-container>
        <v-row flex-wrap>
          <v-col
            :key="i"
            v-for="(item, i) in portfolioItems"
            lg="4"
            md="6"
            sm="6"
            cols="12"
          >
            <v-card class="portfolio-item" shaped>
              <v-card-actions class="grey lighten-2">
                <v-icon color="red" dense class="pl-1 pr-1">mdi-circle</v-icon>
                <v-icon color="yellow" dense class="pr-1">mdi-circle</v-icon>
                <v-icon color="green" dense>mdi-circle</v-icon>
                <v-spacer></v-spacer>
                <v-btn small icon target="_blank" :href="item.link">
                  <v-icon color="222">mdi-open-in-new</v-icon>
                </v-btn>
              </v-card-actions>
              <v-img :src="item.img" :aspect-ratio="16 / 9"> </v-img>
              <v-card-text>
                <v-row class="pa-3 pt-4 pb-1">
                  <div v-for="(tool, x) in item.tools" :key="tool" class="pr-2">
                    <v-chip
                      v-if="x == 0"
                      color="#666"
                      dark
                      label
                      class="font-weight-bold"
                      >{{ tool }}</v-chip
                    >
                    <v-chip v-else label color="#ccc">{{ tool }}</v-chip>
                  </div>
                </v-row>
              </v-card-text>
              <v-card-title class="pt-2 pb-6 mt-1 body-2"
                ><h2>{{ item.title }}</h2></v-card-title
              >

              <!-- <v-card-text class="text--primary pt-0 pb-5">
                <div>Whitsunday Island, Whitsunday Islands</div>
              </v-card-text> -->
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-layout>
  </div>
</template>
<script>
import quotes from "../assets/portfolio/quote-deck.jpg";
import idlekingdoms from "../assets/portfolio/idle-kingdoms.jpg";
import flootie from "../assets/portfolio/flootie-sized.jpg";
import mobius from "../assets/portfolio/MobiusFeature.jpg";
import dylan from "../assets/portfolio/dylan-insurance.png";
import rodda from "../assets/portfolio/rodda-paint.jpg";
import palmBeach from "../assets/portfolio/pba-edu-home.jpg";
import princeton from "../assets/portfolio/princeton-seminary-home.jpg";
export default {
  data: () => ({
    portfolioItems: [
      {
        title: "Princeton Theological Seminary",
        link: "https://ptsem.edu/",
        img: princeton,
        tools: ["2024", "PHP", "WordPress", "Divi"],
      },
      {
        title: "Palm Beach Atlantic University",
        link: "https://www.pba.edu",
        img: palmBeach,
        tools: ["2023", "PHP", "WordPress"],
      },
      {
        title: "Rodda Paint",
        link: "https://www.roddapaint.com",
        img: rodda,
        tools: ["2022", "PHP", "WordPress"],
      },
      {
        title: "Dylan Insurance",
        link: "https://www.dylan-insurance.com",
        img: dylan,
        tools: ["2021", "JavaScript", "React"],
      },
      {
        title: "Mobius Discovery Center",
        link: "https://www.mobiusdiscoverycenter.org",
        img: mobius,
        tools: ["2020", "PHP", "WordPress", "Elementor"],
      },
      {
        title: "Flootie",
        link: "https://www.flootie.com",
        img: flootie,
        tools: ["2018", "HTML", "CSS", "JavaScript"],
      },
      {
        title: "Idle Kingdoms",
        link:
          "https://thinkingdesign.jeremyking.dev/portfolio/2018-idle-kingdoms/",
        img: idlekingdoms,
        tools: ["2018", "JavaScript"],
      },
      {
        title: "Quote Deck",
        link:
          "https://thinkingdesign.jeremyking.dev/portfolio/2016-Quote-Deck/",
        img: quotes,
        tools: ["2016", "JavaSript"],
      },
    ],
  }),
};
</script>

<style lang="scss">
.featuredText {
  width: 750px;
}
.portfolio-item {
  border-radius: 15px !important;
  //   .card-info {
  //     background-color: rgba(0, 0, 0, 0.6);
  //     overflow: hidden;
  //     // height: 0px;
  //     height: 0px;
  //     transition: all 0.3s ease-in-out;
  //   }
  // }
  // .portfolio-item:hover {
  //   .card-info {
  //     height: 66px;
  //   }
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
