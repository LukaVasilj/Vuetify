<template>
  <v-app id="inspire">
    <v-app-bar
      app
      color="white"
      flat
    >
      

      <v-tabs
        centered
        class="ml-n9"
        color="grey darken-1"
      >
        <v-tab
          
        >
          
        </v-tab>
      </v-tabs>

      
    </v-app-bar>

    <v-main class="grey lighten-10">
      <v-container>
        <v-row>
          

          <v-col
            cols="12"
            sm="12"
            
          >
            <v-sheet
              min-height="80vh"
              rounded="lg"
            >
              <div>
                <v-col  sm="7" >
                  
                
          <v-textarea
          label="One row"
          auto-grow
          outlined
          rows="1"
          row-height="15"
          v-model="ticket.subject"
          class="textfield"
        ></v-textarea>

        <v-select
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
    <v-btn class="gumbovi">
<v-icon>mdi-fullscreen</v-icon>
  </v-btn>
  <v-btn class="gumbovi1">
<v-icon>mdi-image</v-icon>
  </v-btn>
  <v-btn class="gumbovi1">
<v-icon>mdi-undo</v-icon>
  </v-btn>
  <v-btn class="gumbovi1">
<v-icon>mdi-redo</v-icon>
  </v-btn>
    
  
    </v-app-bar>

    

    <textarea
      outlined
      counter
      label="Textasa"
      :rules="rules"
      :value="value"
      class="textarea">
    </textarea>
  </v-card>
    
    <v-btn
  elevation="2"
  outlined
  v-on:click="addUser()"
  id="gumb"
  > Upri me </v-btn>
                




                
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
        "subject": null,
        "body": null
      },
      items: ['Foo', 'Bar', 'Fizz', 'Buzz'],
    
      
    };
  },
  methods: {
    async addUser() {
      let result =await axios.post(process.env.VUE_APP_WHATEVERYOUWANT, this.ticket);
      console.warn(result);
    },
    staima(){

    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.textfield{
  margin-bottom:20px;
  
}
.textarea{
  width:100%;
  height:255px;
}
#gumb{
  margin-top:15px;
}
.gumbovi{
  margin-top:14px;
  
}
.gumbovi1{
  margin-top:14px;
  margin-left:3px;
  
}

</style>