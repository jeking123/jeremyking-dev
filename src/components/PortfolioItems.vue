<template>
  <v-layout>
    <v-container>
      <v-row v-if="location == 'home'" class="masonry-row">
        <v-col
          v-for="(column, colIndex) in getDistributedItems(
            portfolioItems.slice(0, 3),
            3
          )"
          :key="colIndex"
          class="masonry-col"
        >
          <div
            v-for="(item, itemIndex) in column"
            :key="itemIndex"
            class="masonry-item"
          >
            <PortfolioItem
              :title="item.title"
              :image="item.img"
              :link="item.link"
              :tools="item.tools"
            />
          </div>
        </v-col>
      </v-row>
      <v-row v-if="location == 'portfolio'" class="masonry-row">
        <v-col
          v-for="(column, colIndex) in getDistributedItems(portfolioItems, 3)"
          :key="colIndex"
          class="masonry-col"
        >
          <div
            v-for="(item, itemIndex) in column"
            :key="itemIndex"
            class="masonry-item"
          >
            <PortfolioItem
              :title="item.title"
              :image="item.img"
              :link="item.link"
              :tools="item.tools"
              :location="location"
              :description="item.description"
              :agency="item.agency"
              :year="item.year"
            />
          </div>
        </v-col>
      </v-row>
      <v-row v-if="location == 'design'" class="masonry-row">
        <v-col
          v-for="(column, colIndex) in getDistributedItems(design, 3)"
          :key="colIndex"
          class="masonry-col"
        >
          <div
            v-for="(item, itemIndex) in column"
            :key="itemIndex"
            class="masonry-item"
          >
            <PortfolioItem
              :title="item.title"
              :image="item.img"
              :link="item.link"
              :tools="item.tools"
              :location="location"
              :description="item.description"
              :agency="item.agency"
              :year="item.year"
            />
          </div>
        </v-col>
      </v-row>
      <v-row v-if="location == 'archive'">
        <Archive :data="allItems" />
      </v-row>
    </v-container>
  </v-layout>
</template>

<script>
// Components
import PortfolioItem from "../components/PortfolioItem";
import Archive from "../components/Archive";

// Web Images
import quotes from "../assets/portfolio/quote-deck.jpg";
import gradshow from "../assets/portfolio/2016-spectrum-gradshow.jpg";
import idlekingdoms from "../assets/portfolio/idle-kingdoms.jpg";
import flootie from "../assets/portfolio/flootie-sized.jpg";
import mobius from "../assets/portfolio/MobiusFeature.jpg";
import dylan from "../assets/portfolio/dylan-insurance.png";
import rodda from "../assets/portfolio/rodda-paint.jpg";
import palmBeach from "../assets/portfolio/pba-edu-home.jpg";
import princeton from "../assets/portfolio/princeton-seminary-home.jpg";

// Design Images
import ultimateFlaps from "../assets/portfolio/design/ultimateflaps-home.png";
import mobiusDesign from "../assets/portfolio/design/mobius-home.png";
import tempest from "../assets/portfolio/design/tempest-poster.png";
import avenueQ from "../assets/portfolio/design/avenue-q-poster.png";
import garbage from "../assets/portfolio/design/garbage-gyre.png";
import heathers from "../assets/portfolio/design/heathers-poster.png";
import recoveringTheClassics from "../assets/portfolio/design/recovering-the-classics-king-arthur.png";
import chinaDragon from "../assets/portfolio/design/china-dragon-menu.jpg";
import takaosan from "../assets/portfolio/design/takaosan-poster.jpg";
import wireharp from "../assets/portfolio/design/wireharp.jpg";

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
        year: "2024",
        tools: ["PHP", "WordPress", "ACF", "Gutenberg", "Custom Theme"],
        description:
          "Led backend development for a custom WordPress theme, collaborating closely with frontend developers to translate design requirements into a scalable solution tailored for the client.",
        agency: "Carnegie Higher Ed",
      },
      {
        title: "Palm Beach Atlantic University",
        link: "https://www.pba.edu",
        img: palmBeach,
        year: "2023",
        tools: ["PHP", "WordPress", "ACF", "Custom Theme"],
        description:
          "Developed a custom theme alongside frontend developers to ensure seamless integration of the client’s design vision with strong technical performance.",
        agency: "Carnegie Higher Ed",
      },
      {
        title: "Rodda Paint",
        link: "https://www.roddapaint.com",
        img: rodda,
        year: "2022",
        tools: ["PHP", "WordPress", "ACF"],
        description:
          "Implemented a custom WordPress theme with advanced plugin integrations and product catalog features, including a dynamic system for displaying product codes, specifications, and related resources.",
        agency: "Brand It Advertising",
      },
      {
        title: "Dylan Insurance",
        link: "https://www.dylan-insurance.com",
        img: dylan,
        year: "2021",
        tools: ["Design", "JavaScript", "HTML", "CSS", "React"],
        description:
          "Designed and developed a Mock React-based site in collaboration with EIG Technologies, creating an interactive frontend demo to showcase the client’s chatbot-driven insurance services.",
        agency: "Freelance",
      },
      {
        title: "Mobius Discovery Center",
        link: "https://mobiusdiscoverycenter.org",
        img: mobius,
        year: "2020",
        tools: ["PHP", "WordPress", "Elementor"],
        description:
          "Redesigned and rebuilt the client’s WordPress site, incorporating dynamic content features for exhibits and events while modernizing the overall look and feel to better engage visitors.",
        agency: "ScannedMedia",
      },
      {
        title: "Flootie",
        link: "https://www.flootie.com",
        img: flootie,
        year: "2018",
        tools: ["Design", "HTML", "CSS", "JavaScript"],
        description:
          "Developed a refreshed homepage and interior templates with clean, responsive frontend code, delivering a modernized user experience for the client’s backend team to integrate.",
        agency: "ScannedMedia",
      },
      {
        title: "Idle Kingdoms Game",
        link: "https://thinkingdesign.jeremyking.dev/portfolio/2018-idle-kingdoms/",
        img: idlekingdoms,
        year: "2018",
        tools: ["Design", "JavaScript", "Vue"],
        description:
          "Created a browser-based incremental game using Vue.js as a personal project to expand coding skills. Players manage resources and workers to grow and expand a medieval kingdom.",
        agency: "Personal",
      },
      {
        title: "SFCC Gradshow Website",
        link: "https://jeremyking.dev/class2016/",
        img: gradshow,
        year: "2016",
        tools: ["Design", "HTML", "CSS", "JavaScript"],
        description:
          "Developed the official website for Spokane Falls Community College’s senior design showcase. Collaborated with classmates under a tight deadline to deliver an industry-selected design concept.",
        agency: "Spokane Falls Community College",
      },
      {
        title: "Quote Deck Component",
        link: "https://thinkingdesign.jeremyking.dev/portfolio/2016-Quote-Deck/",
        img: quotes,
        year: "2016",
        tools: ["Design", "JavaScript", "jQuery"],
        description:
          "Built a creative digital business card concept where users can flip through a virtual deck of playing cards, each featuring a unique quote alongside personal contact information.",
        agency: "Personal",
      },
    ],
    archiveDev: [
      {
        title: "Luther College",
        link: "luther.edu",
        img: "luthercollege",
        year: "2023",
        tools: ["PHP", "WordPress", "ACF"],
        description:
          "Assisted development of backend features, and improved dynamic sidebar functionality",
        agency: "Carnegie Higher Ed",
      },
      {
        title: "Babbs Transportation App",
        link: "/",
        img: princeton,
        year: "2020",
        tools: ["Design", "React", "node.js", "Express", "MongoDB"],
        description:
          "Transportation mangement app for to modernize delivery process from paper to digital tracking and scanning of packages.",
        agency: "ScannedMedia",
      },
      {
        title: "Ultimate Truck",
        link: "https://www.ultimatetruck.com",
        img: "ultimateTruck",
        year: "2022",
        tools: ["PHP", "WordPress", "DIVI"],
        description:
          "Design Implementation for Ultimate Truck using the divi builder.",
        agency: "Brand It Advertising",
      },
      {
        title: "Spokane Valley Fire Department",
        link: "https://www.spokanevalleyfire.org",
        img: "spokaneValleyFire",
        year: "2022",
        tools: ["PHP", "WordPress", "Divi"],
        description:
          "Implemented website design in divi for Spokane Valley Fire Department.",
        agency: "Brand It Advertising",
      },
    ],
    design: [
      {
        title: "Ultimate Flaps Web Design",
        link: "https://ultimateflaps.com",
        img: ultimateFlaps,
        year: "2021",
        tools: ["Design", "Adobe XD", "Photoshop"],
        description:
          "Fresh website design for Ultimate Flaps custom mudflaps for trucks and vehicles.",
        agency: "Brand It Advertising",
      },
      {
        title: "Mobius Discovery Center Web Design",
        link: "https://mobiusdiscoverycenter.org",
        img: mobiusDesign,
        year: "2020",
        tools: ["Design", "Adobe XD", "Photoshop"],
        description:
          "Redesigned website for Mobius Discovery Center, combining their two locations into one cohesive site.",
        agency: "ScannedMedia",
      },
      {
        title: "China Dragon Menu",
        description: "Restaurant menu design for local chinese restaurant.",
        link: "https://www.chinar.com/",
        tools: ["Illustrator"],
        img: chinaDragon,
        year: "2020",
        agency: "ScannedMedia",
      },
      {
        title: "Tempest Theatre Poster",
        description:
          "Poster design for Eastern Washington University Theatre's production of The Tempest.",
        link: "https://www.ewu.edu/news/qa-with-the-tempest-director-jeff-sanders/",
        tools: ["Illustrator"],
        img: tempest,
        year: "2018",
        agency: "Eastern Washington University Theatre",
      },
      {
        title: "Avenue Q Poster",
        description:
          "Poster design for Eastern Washington University Theatre's production of Avenue Q.",
        link: "/",
        tools: ["Illustrator"],
        img: avenueQ,
        year: "2018",
        agency: "Eastern Washington University Theatre",
      },
      {
        title: "Garbage Gyre Poster",
        description: "Awareness poster for Pacific Garbage Gyre.",
        link: "/",
        tools: ["Illustrator"],
        img: garbage,
        year: "2017",
        agency: "Undergrad",
      },
      {
        title: "Heathers Poster",
        description:
          "Poster design for Eastern Washington University Theatre's production of Heathers.",
        link: "/",
        tools: ["Illustrator"],
        img: heathers,
        year: "2017",
        agency: "Eastern Washington University Theatre",
      },
      {
        title: "Recovering the Classics Poster",
        description: "Designed a poster for Recovering the Classics.",
        link: "https://creativeaction.network/products/king-arthur-and-the-knights-of-the-round-table-by-jeremy-king",
        tools: ["Illustrator"],
        img: recoveringTheClassics,
        year: "2018",
        agency: "Creative Action Network",
      },
      {
        title: "Takaosan Poster",
        description: "Designed a poster for Takaosan.",
        link: "https://www.takaosan.com/",
        tools: ["Illustrator"],
        img: takaosan,
        year: "2018",
        agency: "Undergrad",
      },
      {
        title: "Wireharp Book",
        description:
          "Design and layout for WireHarp Creative Lit book for SFCC.",
        link: "https://www.wireharp.com/",
        tools: ["InDesign"],
        img: wireharp,
        year: "2016",
        agency: "Spokane Falls Community College Wireharp",
      },
    ],
  }),
  computed: {
    allItems() {
      return this.combineData(
        this.portfolioItems,
        this.design,
        this.archiveDev
      );
    },
  },
  methods: {
    getDistributedItems(items, columnCount) {
      const columns = Array.from({ length: columnCount }, () => []);

      items.forEach((item, index) => {
        const columnIndex = index % columnCount;
        columns[columnIndex].push(item);
      });

      return columns;
    },
    combineData(...arrays) {
      return [].concat(...arrays).sort((a, b) => b.year - a.year);
    },
  },
};
</script>

<style lang="scss">
.masonry-row {
  display: flex !important;
  align-items: flex-start;
  gap: 24px;

  .masonry-col {
    flex: 1;
    display: flex !important;
    flex-direction: column;
    padding: 0 !important;

    .masonry-item {
      margin-bottom: 24px;

      &:last-child {
        margin-bottom: 0;
      }
    }
  }

  // Responsive breakpoints
  @media (max-width: 960px) {
    gap: 20px;

    .masonry-col .masonry-item {
      margin-bottom: 20px;
    }
  }

  @media (max-width: 600px) {
    flex-direction: column;
    gap: 16px;

    .masonry-col {
      width: 100%;

      .masonry-item {
        margin-bottom: 16px;
      }
    }
  }
}
</style>
