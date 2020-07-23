<template>
  <v-form
  >
    <v-text-field
      v-model="subject"
      label="Subject"
      required
      filled
    ></v-text-field>

    <v-textarea
        v-model="message"
        label="Your message"
        required
        filled>
    </v-textarea>

    <v-btn
      color="primary"
      tile
      class="mr-4"
      @click="submit"
      width="200px"
    >
      Submit
    </v-btn>
  </v-form>
</template>


<script>
  export default {

    data() {
        return {
            subject: "",
            message: ""
        }
    },
    methods: {
      submit () {

        window.open("mailto:samcparker@protonmail.com?subject=" + this.subject + "&body=" + this.message);
      }
    },
  }
</script>