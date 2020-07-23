<template>
  <v-app dark>
    <v-app-bar style="background-color: rgb(0, 0, 0, 0); opacity: 0.5" tile elevation="0" fixed inverted-scroll >
      <v-img style="max-width: 50px; max-height: 50px"  src="/logo.png"></v-img>
      <v-toolbar-title class="tb pl-4" >Sam C. Parker</v-toolbar-title>
      <v-spacer></v-spacer>
      <!-- <a href="#work" class="white--text">My Work</a>
      <a href="#contact" class="white--text pl-4">Contact Me</a> -->
      <v-btn href="#work" tile outlined style="width: 150px">My Work</v-btn>
      <v-btn href="#contact" tile outlined style="width: 150px" class="ml-5">Contact Me</v-btn>
      <!-- <v-app-bar-nav-icon></v-app-bar-nav-icon> -->
    </v-app-bar>
    <v-main>
      <nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {

}
</script>

<style>
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
</style>