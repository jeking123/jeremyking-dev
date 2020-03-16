<template>
  <div class="background">
    <v-layout d-flex flex-wrap align-center>
      <v-flex xs12 sm6 offset-sm3>
        <v-row align="center" justify="center" wrap>
          <v-col class="col-12 d-flex justify-center">
            <v-img alt="jeremy" src="../assets/Jeremy-avatar-2.png" max-width="200" />
          </v-col>
          <v-col>
            <div class="pa-6" max-width="350px">
              <h1>Hi, I'm Jeremy</h1>
              <p>I'm a frontend developer in Spokane, WA. I've been transitioning from design to development over the last couple of years and I'm always excited to talk about new opportunities.</p>
              <v-btn to="/portfolio" outlined>See some of my work.</v-btn>
            </div>
          </v-col>
        </v-row>
        <!-- <v-row>
          <v-col v-bind:key="col.id" v-for="col in content.fields">
            <v-card max-width="300px" class="pa-5">
              <v-container>
                <v-row justify="center">
                  <v-col>
                    <v-icon large class="d-flex justify-center">{{col.icon}}</v-icon>
                    <v-card-title block class="d-flex justify-center">{{col.title}}</v-card-title>
                    <v-divider class="mb-5"></v-divider>
                    <v-card-content>{{col.text}}</v-card-content>
                  </v-col>
                </v-row>
              </v-container>
            </v-card>
          </v-col>
        </v-row>-->
      </v-flex>
      <!-- <div class="copyright text-center pa-3">© copyright Jeremy King 2020</div> -->
    </v-layout>
  </div>
</template>

<script>
export default {
  name: "Home"
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
</style>