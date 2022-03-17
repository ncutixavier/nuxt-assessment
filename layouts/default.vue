<template>
  <v-app dark>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      :color="this.$nuxt.$route.path !== '/' ? 'white' : ''"
      elevation="0"
    >
      <v-avatar tile size="35">
        <img src="~/assets/img/logo.png" alt="John" />
      </v-avatar>
      <v-spacer />
      <v-btn
        text
        color="primary"
        nuxt
        to="/"
        v-if="this.$nuxt.$route.path !== '/'"
      >
        Exit
      </v-btn>
    </v-app-bar>

    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

    <!-- <v-footer :absolute="fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer> -->
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js",
    };
  },
  created() {
    console.log("DefaultLayout created", this.$nuxt.$route.path);
  },
};
</script>
