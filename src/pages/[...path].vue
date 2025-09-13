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
            <h1 class="mt-1 text-blue-grey">404 not found</h1>
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
            "I’m a developer who specializes in bridging design and development to build fast, accessible, and visually polished websites. My work centers on transforming thoughtful design into robust code, creating digital experiences that balance aesthetics with performance and usability. My focus is to help organizations with custom WordPress themes, React applications, and performance-optimized solutions. I focus on the best approach to development for my clients, delivering sites that are flexible for editors while staying lightweight and future-ready.",
        },
        {
          heading: "Thanks for stoping by!",
          paragraph:
            "I’ve collaborated with universities, nonprofits, start-ups, and small businesses, giving me experience across theme and plugin development, SEO, automation, and full-stack applications. Beyond client work, I explore the creative side of design and development through indie game projects and interactive tools that combine storytelling with technology. Outside of work, you’ll often find me playing D&D, experimenting with new game concepts, out on a disc golf course, or tinkering with fresh ideas that bring design and code together.",
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
