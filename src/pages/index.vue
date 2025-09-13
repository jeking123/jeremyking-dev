<template>
  <div class="background pt-md-16 pb-md-16 pt-sm-8 pb-sm-8">
    <!-- <v-img class="background"> -->
    <v-container
      d-flex
      max-width="1200px"
      min-height="600px"
      class="fill-height align-content-center"
    >
      <v-row>
        <v-col>
          <div class="bubble bubble-bottom-left">
            <v-carousel
              v-model="slide"
              :show-arrows="false"
              hide-delimiters
              height="auto"
              class="d-flex align-center"
            >
              <v-carousel-item v-for="(item, i) in intro" :key="i">
                <h2 class="pb-2 text-blue-grey">
                  {{ item.heading }}
                </h2>
                <p class="ma-0">
                  {{ item.paragraph }}
                </p>
              </v-carousel-item>
            </v-carousel>
            <v-row>
              <v-col>{{ slide + 1 }} / {{ intro.length }}</v-col>
              <v-col>
                <div class="d-flex justify-end">
                  <button @click="slide > 0 ? slide-- : ''">
                    <v-icon icon="mdi-menu-left" />
                  </button>
                  <button @click="slide + 1 < intro.length ? slide++ : ''">
                    <v-icon icon="mdi-menu-right" />
                  </button>
                </div>
              </v-col>
            </v-row>
          </div>
        </v-col>
      </v-row>
      <v-row>
        <v-col class="col-12 d-flex justify-left">
          <v-img
            class="avatar"
            alt="jeremy"
            src="../assets/Jeremy-avatar-2.png"
            max-width="200"
          />
        </v-col>
      </v-row>
    </v-container>
  </div>
  <v-container class="pt-4 pb-8">
    <v-row>
      <v-col>
        <v-sheet
          class="d-flex align-center justify-center flex-wrap text-center mx-auto px-4"
          height="150"
          max-width="800"
          width="100%"
        >
          <div>
            <h2 class="text-h4 font-weight-black text-blue-grey">
              {{ portfolioContent.title }}
            </h2>

            <div class="text-h5 font-weight-medium mb-2">
              <p>
                {{ portfolioContent.desc }}
              </p>
            </div>
          </div>
        </v-sheet>

        <PortfolioItems location="home" />

        <v-sheet
          class="d-flex align-center justify-center flex-wrap text-center mx-auto px-4"
          height="50"
          max-width="800"
          width="100%"
        >
          <div>
            <v-btn
              color="blue-grey"
              :to="portfolioContent.link.to"
              :text="portfolioContent.link.text"
              variant="text"
            />
          </div>
        </v-sheet>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import PortfolioItems from "../components/PortfolioItem";
export default {
  name: "Home",
  components: {
    PortfolioItems,
  },
  data() {
    return {
      slide: 0,
      intro: [
        {
          heading: "Hi, I'm Jeremy King",
          paragraph:
            "I'm a developer specializing in bridging design and development to build fast, accessible, and visually polished websites. I transform thoughtful design into robust code, creating digital experiences that balance aesthetics with performance and usability. My expertise lies in crafting custom WordPress themes and React applications that are performant, flexible for content editors, and built to be future-ready.",
        },
        {
          heading: "Thanks for stoping by!",
          paragraph:
            "I have collaborated with universities, nonprofits, start-ups, and small businesses, gaining extensive experience in design, theme and plugin development, SEO, automation, and full-stack applications. Beyond client work, I explore the creative side of technology through indie game projects and interactive tools that combine storytelling with code. Outside of work, you’ll find me playing D&D, experimenting with game concepts, out on a disc golf course, or tinkering with new ideas that bring design and code together.",
        },
      ],
      portfolioContent: {
        title: "Portfolio",
        desc: "Some of my recent work",
        link: {
          text: "View All Projects",
          to: "/portfolio",
        },
      },
    };
  },
};
</script>

<style lang="scss">
.background {
  background: linear-gradient(45deg, rgba(100, 200, 200), white);
}
.bubble {
  position: relative;
  font-family: sans-serif;
  font-size: 18px;
  line-height: 24px;
  width: 75%;
  background: #fff;
  border-radius: 40px;
  padding: 24px;
  text-align: left;
  color: #000;
  margin-left: 140px;
}

.bubble-bottom-left:before {
  content: "";
  width: 0px;
  height: 0px;
  position: absolute;
  border-left: 24px solid #fff;
  border-right: 12px solid transparent;
  border-top: 12px solid #fff;
  border-bottom: 20px solid transparent;
  left: 75px;
  bottom: -24px;
}

@media only screen and (max-width: 600px) {
  .bubble {
    position: relative;
    font-family: sans-serif;
    font-size: 18px;
    line-height: 24px;
    width: 75%;
    background: #fff;
    border-radius: 40px;
    padding: 24px;
    text-align: left;
    color: #000;
    margin-left: 50px;
  }
  .avatar {
    .v-image__image {
      width: 125px;
      height: 125px;
      background-size: contain;
    }
  }
}
</style>
