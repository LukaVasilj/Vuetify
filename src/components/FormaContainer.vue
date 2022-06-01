<template>
    <v-container class="container">
        <v-row>
          <v-col cols="12" sm="12">
            <v-sheet min-height="80vh" rounded="lg">
              <div>
                <v-col sm="7">

                  <v-textarea
                    color="deep-purple accent-4"
                    label="Predmet"
                    auto-grow
                    outlined
                    rows="1"
                    row-height="15"
                    v-model="ticket.subject"
                    class="textfield"
                  ></v-textarea>

                  <v-select
                    color="deep-purple accent-4"
                    :items="items"
                    label="Outlined style"
                    outlined
                    class="textfield"
                  ></v-select>

                  <tiket-body/>
                   
                  <v-btn
                    elevation="2"
                    outlined
                    v-on:click="addUser()"
                    id="gumb"
                  >
                    Upri me
                  </v-btn>

                  
                  
                </v-col>
              </div>
            </v-sheet>
          </v-col>
        </v-row>
    </v-container>
</template>

<script>
import TiketBody from './TiketBody.vue'
import axios from "axios";
export default {
    components: { TiketBody },
    data() {
    return {
      ticket: {
        subject: null,
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
    staima() {},
  },
  mounted() {
    let Script = document.createElement("script");
    Script.setAttribute("src", "https://cdn.jsdelivr.net/npm/vue/dist/vue.js");
    document.head.appendChild(Script);

    document.getElementById("buttonn").addEventListener("click", loadText);
    function loadText() {
      console.log("button");
    }
  
    const image_input = document.querySelector("#image-input");

    image_input.addEventListener("change", function () {
      const reader = new FileReader();
      reader.addEventListener("load", () => {
        const uploaded_image = reader.result;
        document.querySelector(
          "#display-image"
        ).style.backgroundImage = `url(${uploaded_image})`;
      });
      reader.readAsDataURL(this.files[0]);
    });
  },
}
</script>

<style>

</style>