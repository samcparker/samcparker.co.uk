<template>
  <v-app dark>
    <v-app-bar style="background-color: rgb(0, 0, 0, 0);" class="hoveropacity" tile elevation="0" fixed inverted-scroll >
      <a href="#">
        <v-img style="max-width: 50px; max-height: 50px"  src="/logo.png"></v-img>
      </a>
      <!-- <v-toolbar-title class="tb pl-4" >Sam C. Parker</v-toolbar-title> -->
      <v-spacer></v-spacer>
      <!-- <a href="#work" class="white--text">My Work</a>
      <a href="#contact" class="white--text pl-4">Contact Me</a> -->
      <div class="hidden-sm-and-down">
        <v-btn href="#work" tile outlined style="width: 150px" small>My Work</v-btn>
        <v-btn href="#contact" tile outlined style="width: 150px" class="ml-5" small>Contact Me</v-btn>
      </div>
      <v-app-bar-nav-icon class="hidden-md-and-up" @click="drawer = !drawer"></v-app-bar-nav-icon>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" right dark app color="#121212">
      <v-list>
        <v-list-item class="mt-5" link href="#work">
          <v-list-item-avatar tile>
              <img src="/logo.png">
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title class="titled">
                Sam C. Parker
              </v-list-item-title>
            </v-list-item-content>
        </v-list-item>
        <v-spacer class="my-5"></v-spacer>
        <v-list-item link href="#work">
          <v-list-item-content>
            <v-list-item-title class="sub">
              My Work
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link href="#contact">
          <v-list-item-content>
            <v-list-item-title  class="sub">
              Contact Me
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

    </v-navigation-drawer>
    <v-main>
      <nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false
    }
  }
}
</script>

<style>
  .hoveropacity {
    opacity: 0.5;
    transition: transform 610ms, opacity 610ms;
  }

  .hoveropacity:hover {
    opacity: 1;
  }

  html {
    scroll-behavior: smooth;
  }

  h1 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
    font-size: 60px;
  }
  h2 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
    font-size: 50px;
  }

  h3 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
    font-size: 30px;
  }

  p {
    font-family: 'Montserrat', sans-serif;
    font-weight: 300;
    font-size: 18px;
  }

  .tb {
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
    font-size: 30px;
  }

  .titled {
    font-family: 'Montserrat', sans-serif;
    font-weight: 300;
    font-size: 20px;
  }

  .sub {
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
    font-size: 30px;
  }
</style>