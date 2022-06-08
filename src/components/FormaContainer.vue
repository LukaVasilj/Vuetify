<template>
  <v-container class="container">
    <v-layout row justify-space-between align-center>
      <v-flex xs6 md3>
        <p>Novi tiket</p>
      </v-flex>
      <v-flex xs6 md3>
        <v-btn class="lista"
          >Prikaži<br />
          prethodne tikete</v-btn
        >
      </v-flex>
    </v-layout>

    <v-layout row>
      <v-flex xs12 md12>
        <v-sheet class="sheet" rounded="lg">
          <v-layout row justify-center>
            <v-flex xs7 md7>
              <!-- Tiket subject !-->
              <v-textarea
                class="subject-area"
                color="black"
                label="Predmet"
                auto-grow
                outlined
                rows="1"
                v-model="ticket.subject"
              ></v-textarea>
              <!-- Tiket department !-->
              <v-select
                color="black"
                :items="items"
                label="Odjel"
                outlined
                v-model="ticket.department"
              ></v-select>
              <!-- Tiket body !-->
              <!-- Tiket submit !-->
              <v-btn elevation="2" outlined v-on:click="addUser()" id="gumb">
                Upri me
              </v-btn>
            </v-flex>
          </v-layout>
        </v-sheet>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      ticket: {
        subject: null,
        department: null,
        body: null,
      },
      items: ["Foo", "Bar", "Fizz", "Buzz"],
    };
  },
  methods: {
    async addUser() {
      let result = await axios.post(
        process.env.VUE_APP_LINKZATIKETAPI,
        this.ticket
      );
      console.warn(result);
    },
  },
};
</script>

<style>
@import "../assets/css/FormaContainer.css";
</style>