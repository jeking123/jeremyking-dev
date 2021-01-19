<template>
  <div class="resume">
    <v-container>
      <v-row class="resume-content">
        <v-col md="7" sm="7">
          <div class="headline">
            <h1 class="mb-6">Hello,</h1>
            <p>Thank you for stopping by. I'm always looking to meet local professionals, or talk about new opportunities. I've spent the last few years transitioning from design to development, learning, and applying myself to new challenges every day. I'm excited and looking to excel at whatever next comes my way.</p>
            <p>~ Jeremy King</p>
          </div>
          <div class="pt-6">
            <h3 class="mb-2">Work History:</h3>
            <v-divider class="pb-3"></v-divider>
            <div class="pb-4" :key="i" v-for="(work, i) in work">
              <div class="font-weight-bold">{{work.position}}</div>
              <!-- <v-divider></v-divider> -->
              <div class="d-flex flex-wrap">
                <div class="pr-2 body-2">{{work.place}}</div>
                <div class="pr-2 body-2">
                  <v-icon>mdi-map-marker</v-icon>
                  {{work.location}}
                </div>
                <div class="pr-2 body-2">
                  <v-icon>mdi-calendar</v-icon>
                  {{work.start}} to {{work.end}}
                </div>
              </div>
              <v-divider></v-divider>
            </div>
          </div>
        </v-col>
        <v-col md="5" sm="5">
          <h3 class="mb-2">Things I have experience with:</h3>
          <div class="d-flex flex-wrap">
            <v-card class="ma-1" :key="i" v-for="(card, i) in tags" outlined>
              <v-card-text class="pa-2">{{card}}</v-card-text>
            </v-card>
          </div>
          <div class="pt-6">
            <h3 class="mb-2">My Education:</h3>
            <v-divider></v-divider>
            <div :key="i" v-for="(edu, i) in education">
              <div class="pt-2 font-weight-bold">{{edu.place}}</div>
              <div class="pb-2">
                <div>
                  <span class="font-italic">
                    Graduated in {{edu.grad}} with a
                    {{edu.degree}}
                  </span>
                </div>
              </div>
              <v-divider></v-divider>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    tags: [
      "HTML/CSS",
      "Vue.js",
      "React",
      "Hanging Out",
      "WordPress",
      "Javascript",
      "Video Games",
      "Node/Express",
      "GraphQL",
      "MongoDB",
      "Pen & Paper",
      "SCSS",
      "GitHub",
      "Terminal",
      "Visual Studio Code",
      "NPM",
      "ES6",
      "Board Games",
      "Shopify",
      "Liquid",
      "Jekyll",
      "UI/UX",
      "PC Building",
      "Adobe Creative Suite",
      "Wireframing",
      "Project Outlining",
      "Design Thinking"
    ],
    education: [
      {
        place: "Eastern Washington University",
        degree: "BA in Visual Communication Design",
        grad: "2018"
      },
      {
        place: "Spokane Falls Community College",
        degree: "AAS-T in Graphic Design",
        grad: "2016"
      }
    ],
    work: [
      {
        place: "scannedMedia Creative Firm",
        position: "Web Developer",
        location: "Spokane, WA",
        start: "May 2019",
        end: "Present"
      },
      {
        place: "Freelance",
        position: "Designer / Developer",
        location: "Spokane, WA",
        start: "Jan 2016",
        end: "Present"
      },
      {
        place: "Eastern Washington University Theatre",
        position: "Assitant Graphic Designer",
        location: "Cheney, WA",
        start: "Sep 2016",
        end: "June 2018"
      },
      {
        place: "SFCC Wire Harp",
        position: "Assitant Graphic Designer",
        location: "Spokane, WA",
        start: "Sep 2015",
        end: "May 2016"
      },
      {
        place: "scannedMedia",
        position: "Graphic Design Internship",
        location: "Spokane, WA",
        start: "Sep 2015",
        end: "Dec 2015"
      }
    ]
  })
};
</script>

<style lang="scss">
@media only screen and (max-width: 600px) {
  .resume-content {
    flex-flow: column;
  }
}
</style>