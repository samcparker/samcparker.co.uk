<template>
  <v-container >
    <section id="landing">
      <v-container :style="style" fill-height class="main-con">
        <v-row class="mx-0">
          <v-col class="px-0">
            <v-container>
              <v-row class="mx-0 mb-3" align="center">
                <v-img style="max-width: 50px; height: 50px" src="/logo.png" class="mr-3"></v-img>
                  <h1 class="" style="width: 100%; word-wrap: break-word;">Sam C. Parker</h1>
              </v-row>

                <p class="mb-5">I take great ideas and turn them into functional websites.</p>
                <v-row class="mx-0" style="max-width: 375px" id="scroll-target">
                  <v-col class="px-0 pr-2" cols="6">
                    <v-btn width="100%" color="primary" href="#work" tile >See Work</v-btn>
                  </v-col>
                  <v-col class="px-0 pl-2" cols="6">
                    <v-btn width="100%" color="white" href="#contact" outlined tile>Contact Me</v-btn>
                  </v-col>
                </v-row>
                <v-row justify="center">
                  <!-- <p>Scroll Down</p> -->
                  <v-btn href="#work" class="mt-15"  icon>
                    <v-icon x-large>mdi-chevron-down</v-icon>

                  </v-btn>
                </v-row>
                <!-- TODO: Show user they can scroll down somehow -->

            </v-container>
          </v-col>
        </v-row>
      </v-container>
    </section>
    <section id="work">
      <v-container style="max-width: 1200px">
        <h2>My Work</h2>
          <p class="mb-10">Check out some of my previous work.</p>
        <div class="px-5" v-for="(web, index) in websites" :key="index">
          <showcase :data="web" />
          <v-divider class="mt-10 mb-10"></v-divider>
        </div>

      </v-container>
    </section>
    <section id="contact">
      <v-container class="py-15" style="max-width: 1200px; ">
        <h2>Contact Me</h2>
        <p class="mb-10">Want a website or looking to hire? I would love to hear from you.</p>
        <contact-form class="px-5" />
      </v-container>
    </section>
  </v-container>
</template>

<style >
.main-con {
  background: url("/signature-lo.png") no-repeat;
  background-size:contain;
  background-position: center;
}
</style>

<script>

export default {
  async asyncData({ $content }) {
    const websites = await $content("", {deep: true}).where({dir: "/websites"}).sortBy("createdAt", "asc").fetch();
    console.log(websites);
    return { websites };
  },
  data() {
    return {
      screenHeight: null,

    }
  },
  computed: {
    style() {
      return {
        maxWidth: "1200px",
        height: this.screenHeight + "px",
      }
    }
  },
  mounted() {
    var factor = 1;
    this.screenHeight = screen.availHeight * factor;
    window.onresize = () => {
      this.screenHeight = screen.availHeight * factor;
    };
  },
  components: {
  }
}
</script>
