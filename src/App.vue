<template>
  <v-app id="inspire">
    <v-app-bar app color="white" flat>
      
    </v-app-bar>

    <v-main class="grey lighten-10">
      <v-container>
        <v-row>
          <v-col cols="12" sm="12">
            <v-sheet min-height="80vh" rounded="lg">
              <div>
                <v-col sm="7">
                  <v-textarea
                    color="deep-purple accent-4"
                    label="One row"
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

                  <v-card
                    class="mx-auto overflow-hidden"
                    height="340"
                    width="100ram"
                  >
                    <v-system-bar color="deep-purple darken-4"></v-system-bar>

                    <v-app-bar
                      color="deep-purple accent-4"
                      dark
                      prominent
                      height="75"
                    >

                      <v-btn class="gumbovi1">
                        <v-icon>mdi-undo</v-icon>
                      </v-btn>
                      <v-btn class="gumbovi1">
                        <v-icon>mdi-redo</v-icon>
                      </v-btn>

                      <label class="custom-file-upload gumb2">
                        <input
                          type="file"
                          id="image-input"
                          accept="image/jpeg, image/png, image/jpg"
                        />
                        <v-icon id="ikona">mdi-image</v-icon>
                      </label>

                      <v-btn class="gumbovi1" id="buttonn">
                        <v-icon>mdi-fullscreen</v-icon>
                      </v-btn>
                    </v-app-bar>
                    <textarea
                      
                      outlined
                      counter
                      label="Textasa"
                      :rules="rules"
                      :value="value"
                      class="textarea"
                    >
                    </textarea>
                    
                  </v-card>
                   
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
    </v-main>
  </v-app>
</template>

<script>
import axios from "axios";
export default {
  name: "App",
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
};
</script>

<style>
  @import './assets/styles.css';
</style>
