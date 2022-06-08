<template>
  <v-app id="app">
    <v-app-bar 
      class="app-bar" 
      color="white" 
      app 
      flat 
      hide-on-scroll>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-img
        class="logo"
        src="../assets/LogoSumarum.png"
        max-height="150"
        max-width="150"
      ></v-img>
    </v-app-bar>

    <v-main class="grey lighten-10">
      <forma-container />
    </v-main>
  </v-app>
</template>

<script>
import FormaContainer from "./FormaContainer.vue";
export default {
  components: { FormaContainer },
};
</script>

<style>
@import "../assets/css/TiketForma.css";
</style>