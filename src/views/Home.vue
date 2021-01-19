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
                  <h2 class="pb-2">{{ item.h }}</h2>
                  <p class="ma-0">{{ item.p }}</p>
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
            <v-img class="avatar" alt="jeremy" src="../assets/Jeremy-avatar-2.png" max-width="200" />
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
          h: "Hi, I'm Jeremy King",
          p:
            "I'm a frontend developer in Spokane, WA. I graduated from SFCC in 2016 with a Graphic Design AAS-T Degree. Then from Eastern Washington University in 2018 with a BA degree in Visual Communication Design. My university experience led me to explore design thinking, research, conception, ideation, communication, and, how those ideas and processes applied to creative thinking."
        },
        {
          h: "",
          p:
            "I've worked on a variety of projects and am currently employed in Spokane WA, as a frontend developer. I have experience with Wordpress, Shopify, Vue, React & Node. With a strong understanding of HTML, CSS, and JavaScript. I excel at problem-solving and finding a great solution. Whether that's by conducting market research, quick iteration with a framework, or executing a design with handwritten CSS/JS tailored to the issue at hand."
        }
      ]
    };
  }
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
