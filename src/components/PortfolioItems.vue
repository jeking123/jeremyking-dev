<template>
  <v-layout>
    <v-container>
      <v-row v-if="location == 'home'">
        <v-col
          v-for="(item, i) in portfolioItems.slice(0, 3)"
          :key="i"
          lg="4"
          md="6"
          sm="12"
          cols="12"
        >
          <PortfolioItem
            :title="item.title"
            :image="item.img"
            :link="item.link"
            :tools="item.tools"
          />
        </v-col>
      </v-row>
      <v-row v-if="location == 'portfolio'">
        <v-col
          v-for="(item, i) in portfolioItems"
          :key="i"
          lg="4"
          md="6"
          sm="12"
          cols="12"
        >
          <PortfolioItem
            :title="item.title"
            :image="item.img"
            :link="item.link"
            :tools="item.tools"
            :location="location"
          />
        </v-col>
      </v-row>
    </v-container>
  </v-layout>
</template>

<script>
// Components
import PortfolioItem from "../components/PortfolioItem";

// Images
import quotes from "../assets/portfolio/quote-deck.jpg";
import gradshow from "../assets/portfolio/2016-spectrum-gradshow.jpg";
import idlekingdoms from "../assets/portfolio/idle-kingdoms.jpg";
import flootie from "../assets/portfolio/flootie-sized.jpg";
import mobius from "../assets/portfolio/MobiusFeature.jpg";
import dylan from "../assets/portfolio/dylan-insurance.png";
import rodda from "../assets/portfolio/rodda-paint.jpg";
import palmBeach from "../assets/portfolio/pba-edu-home.jpg";
import princeton from "../assets/portfolio/princeton-seminary-home.jpg";

// Data Export
export default {
  components: {
    PortfolioItem,
  },
  props: {
    location: String,
  },
  setup(props) {
    console.log(props.location);
  },
  data: () => ({
    locations: location,
    portfolioItems: [
      {
        title: "Princeton Theological Seminary",
        link: "https://ptsem.edu/",
        img: princeton,
        tools: ["2024", "PHP", "WordPress"],
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
        link: "https://mobiusdiscoverycenter.org",
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
        link: "https://thinkingdesign.jeremyking.dev/portfolio/2018-idle-kingdoms/",
        img: idlekingdoms,
        tools: ["2018", "JavaScript", "Vue"],
      },
      {
        title: "SFCC Gradshow",
        link: "https://jeremyking.dev/class2016/",
        img: gradshow,
        tools: ["2016", "HTML", "CSS", "JavaScript"],
      },
      {
        title: "Quote Deck",
        link: "https://thinkingdesign.jeremyking.dev/portfolio/2016-Quote-Deck/",
        img: quotes,
        tools: ["2016", "JavaSript", "jQuery"],
      },
    ],
  }),
};
</script>

<style>
/* . . . */
</style>
