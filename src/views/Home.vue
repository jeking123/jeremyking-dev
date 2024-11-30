<template>
  <div class="background">
    <v-layout d-flex flex-wrap align-center>
      <v-flex xs12 sm6 offset-sm3>
        <v-row align="center" justify="center" wrap>
          <v-col>
            <div class="bubble bubble-bottom-left">
              <v-carousel
                :show-arrows="false"
                hide-delimiters
                height="auto"
                class="d-flex align-center"
                v-model="slide"
              >
                <v-carousel-item v-for="(item, i) in intro" :key="i">
                  <h2 class="pb-2">{{ item.heading }}</h2>
                  <p class="ma-0">{{ item.paragraph }}</p>
                </v-carousel-item>
              </v-carousel>
              <v-row>
                <v-col>{{ slide + 1 }} / {{ intro.length }}</v-col>
                <v-col>
                  <div class="d-flex justify-end">
                    <button @click="slide--">
                      <v-icon>mdi-menu-left</v-icon>
                    </button>
                    <button @click="slide++">
                      <v-icon>mdi-menu-right</v-icon>
                    </button>
                  </div>
                </v-col>
              </v-row>
            </div>
          </v-col>
          <v-col class="col-12 d-flex justify-left">
            <v-img
              class="avatar"
              alt="jeremy"
              src="../assets/Jeremy-avatar-2.png"
              max-width="200"
            />
          </v-col>
        </v-row>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      slide: 0,
      intro: [
        {
          heading: "Hi, I'm Jeremy King",
          paragraph:
            "I am a Web Developer living in Spokane, WA who loves what they do. I graduated from SFCC in 2016 with a Graphic Design AAS-T Degree. After which, I attended Eastern Washington University where I earned my BA degree in Visual Communication Design. Being able to explore design thinking, research, conception, ideation, communication and how those ideas apply to creative thinking has been one of the best things about my educational experience",
        },
        {
          heading: "",
          paragraph:
            "I'm an experienced developer with a background in frontend development. My skill set includes WordPress, Shopify, Vue, React, Node & PHP. From HTML and CSS to JS; from Design to solving problems – I'm always looking for the most efficient way out of any given situation. Whether that's by conducting market research, quick iteration with a framework, or executing a design with handwritten code tailored to the current issue.",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.background {
  background: linear-gradient(45deg, rgba(100, 200, 200), white);
  height: 100%;

  .layout {
    height: 100%;
  }
  .copyright {
    text-align: center;
    align-self: flex-end;
    width: 100%;
  }
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
