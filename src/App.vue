<template>
  <v-app style="background-color: gray;">
    <v-app-bar color="black" app fixed dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://api.nasa.gov/assets/img/favicons/favicon-192.png"
          transition="scale-transition"
          width="60"
        />
        <label
          ><strong><h1>NASA API</h1></strong></label
        >
      </div>

      <v-spacer />

      <v-btn target="_blank" text @click="toTop">
        <span class="mr-2">Back to the Top Page</span>
        <v-icon>mdi-navigation</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main style="margin-top: 20px">
      <HelloWorld />
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from "./components/NasaAPI";

export default {
  name: "App",

  components: {
    HelloWorld,
  },
  methods: {
    toTop() {
      this.$vuetify.goTo(0);
    },
  },
};
</script>
