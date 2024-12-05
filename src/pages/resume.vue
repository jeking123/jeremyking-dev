<template>
  <div class="resume fill-height">
    <v-container>
      <v-row class="resume-content">
        <v-col md="7" sm="7">
          <div class="headline">
            <h1 class="mb-6">Hello,</h1>
            <p>
              Thank you for stopping by. I'm always looking to meet local
              professionals, or talk about new opportunities. I've spent the
              last few years transitioning from design to development, learning,
              and applying myself to new challenges every day. I'm excited and
              looking to excel at whatever next comes my way.
            </p>
            <p>~ Jeremy King</p>
          </div>
          <div class="pt-6">
            <h3 class="mb-2">Work History:</h3>
            <v-divider class="pb-3" />
            <div v-for="(work, i) in work" :key="i" class="pb-4">
              <div class="font-weight-bold">
                {{ work.position }}
              </div>
              <!-- <v-divider></v-divider> -->
              <div class="d-flex flex-wrap">
                <div class="pr-2 body-2">
                  {{ work.place }}
                </div>
                <div class="pr-2 body-2">
                  <v-icon>mdi-map-marker</v-icon>
                  {{ work.location }}
                </div>
                <div class="pr-2 body-2">
                  <v-icon>mdi-calendar</v-icon>
                  {{ work.start }} to {{ work.end }}
                </div>
              </div>
              <v-divider />
            </div>
          </div>
        </v-col>
        <v-col md="5" sm="5">
          <h3 class="mb-2">Things I have experience with:</h3>
          <div class="d-flex flex-wrap">
            <v-card v-for="(card, i) in tags" :key="i" class="ma-1" outlined>
              <v-card-text class="pa-2">
                {{ card }}
              </v-card-text>
            </v-card>
          </div>
          <div class="pt-6">
            <h3 class="mb-2">My Education:</h3>
            <v-divider />
            <div v-for="(edu, i) in education" :key="i">
              <div class="pt-2 font-weight-bold">
                {{ edu.place }}
              </div>
              <div class="pb-2">
                <div>
                  <span class="font-italic">
                    Graduated in {{ edu.grad }} with a
                    {{ edu.degree }}
                  </span>
                </div>
              </div>
              <v-divider />
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
      "Design Thinking",
    ],
    education: [
      {
        place: "Eastern Washington University",
        degree: "BA in Visual Communication Design",
        grad: "2018",
      },
      {
        place: "Spokane Falls Community College",
        degree: "AAS-T in Graphic Design",
        grad: "2016",
      },
    ],
    work: [
      {
        place: "Carnegie",
        position: "Backend Web Developer",
        location: "Remote",
        start: "Sep 2022",
        end: "Nov 2024",
      },
      {
        place: "Brand It Adversting",
        position: "Web & Digital Specialist",
        location: "Spokane Valley, WA",
        start: "June 2021",
        end: "Sep 2022",
      },
      {
        place: "ScannedMedia Creative Firm",
        position: "Web Developer",
        location: "Spokane, WA",
        start: "May 2019",
        end: "Mar 2021",
      },
      {
        place: "Freelance",
        position: "Designer / Developer",
        location: "Spokane, WA",
        start: "Mar 2016",
        end: "Present",
      },
      {
        place: "Eastern Washington University Theatre",
        position: "University Publicity Graphic Designer",
        location: "Cheney, WA",
        start: "Sep 2016",
        end: "June 2018",
      },
      {
        place: "SFCC Wire Harp",
        position: "Assistant Graphic Designer",
        location: "Spokane, WA",
        start: "Sep 2015",
        end: "May 2016",
      },
    ],
  }),
};
</script>

<style lang="scss">
// . . .
</style>
