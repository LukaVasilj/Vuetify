<template>
  <v-app id="inspire">
    <v-app-bar app color="white" flat>
      
    </v-app-bar>

    <v-main class="grey lighten-10">
      <forma-container />
    </v-main>
  </v-app>
</template>

<script>
import FormaContainer from './FormaContainer.vue'
export default {
    components: { FormaContainer }
}
</script>

<style>
    @import '../assets/css/TiketForma.css';
</style>