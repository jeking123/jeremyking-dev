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
            "I am a Web Developer living in Spokane, WA who loves what they do. I graduated from SFCC in 2016 with a Graphic Design AAS-T Degree. After which, I attended Eastern Washington University where I earned my BA degree in Visual Communication Design. Being able to explore design thinking, research, conception, ideation, communication and how those ideas apply to creative thinking has been one of the best things about my educational experience.",
        },
        {
          heading: "Thanks for stoping by!",
          paragraph:
            "I'm an experienced developer with a background in frontend development. My skill set includes WordPress, Shopify, Vue, React, Node & PHP. From HTML and CSS to JS; from Design to solving problems – I'm always looking for the most efficient way out of any given situation. Whether that's by conducting market research, quick iteration with a framework, or executing a design with handwritten code tailored to the current issue.",
        },
      ],
      portfolioContent: {
        title: "Portfolio",
        desc: "Some of my recent work",
        link: {
          text: "View All Work",
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
