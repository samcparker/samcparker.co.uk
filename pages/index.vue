<template>
  <v-container>
    <v-container style="max-width: 1200px; height: 800px" fill-height>
      <v-row class="mx-0">
        <v-col>
          <v-container>
              <h1 class="mb-5">Sam C. Parker</h1>
              <p>I take beautiful designs and turn them into fully functional websites.</p>
              <v-row class="mx-0" style="max-width: 500px">
                <v-col class="px-0 pr-2" cols="6">
                  <v-btn width="100%" color="primary" href="#work" tile>See Work</v-btn>
                </v-col>
                <v-col class="px-0 pl-2" cols="6">
                  <v-btn width="100%" color="primary" href="#contact" outlined tile>Contact Me</v-btn>
                  

                </v-col>
              </v-row>
          </v-container>
        </v-col>
      </v-row>
    </v-container>
    <section id="work">
      <v-container style="max-width: 1200px">
        <h2>My Work</h2>
          <p class="mb-10">Check out some of my previous work.</p>
        <div v-for="(web, index) in websites" :key="index">
          <showcase :data="web" />
          <v-divider class="mt-10 mb-10"></v-divider>
        </div>

      </v-container>
    </section>
    <section id="contact">
      <v-container class="py-15" style="max-width: 1200px; ">
        <h2>Contact Me</h2>
        <p class="mb-10">Want a website or looking to hire? I would love to hear from you.</p>
        <contact-form/>
      </v-container>
    </section>
  </v-container>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'



export default {
  async asyncData({ $content }) {
    const websites = await $content("", {deep: true}).where({dir: "/websites"}).sortBy("createdAt", "asc").fetch();
    console.log(websites);
    return { websites };
  },
  components: {
    Logo,
    VuetifyLogo
  }
}
</script>
