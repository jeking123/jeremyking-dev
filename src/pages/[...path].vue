<template>
  <div class="fill-height background pt-md-16 pb-md-16 pt-sm-8 pb-sm-8">
    <!-- <v-img class="background"> -->
    <v-container
      d-flex
      max-width="800px"
      min-height="600px"
      class="fill-height align-content-center"
    >
      <v-row>
        <v-col>
          <div class="bubble bubble-bottom-left">
            <h1 class="mt-1">404 not found</h1>
            <p class="mt-4">
              Sorry, I'm not able to find what you're looking for, but here's a
              photo of a cat instead.
            </p>
            <v-sheet class="pt-6">
              <v-img
                min-width="200"
                class="rounded-xl"
                src="https://loremflickr.com/800/800/cat"
              />
            </v-sheet>
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
</template>

<script>
export default {
  name: "404",
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
