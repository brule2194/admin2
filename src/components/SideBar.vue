<template>
  <v-app id="inspire">
    <v-container >
      <v-navigation-drawer v-model="drawer" temporary app>
        <v-sheet color="deep-purple accent-4" class="pa-4">
          <v-avatar class="mb-4" color="grey darken-1" size="64">
            <img src="@/assets/1.jpg" />
          </v-avatar>
            <v-btn class="badge float-right"  icon @click="drawer = !drawer">
              <v-icon color="white">mdi-close</v-icon>
            </v-btn>
          

          <div class="white--text mt-3 headline">blhidalgo@uci</div>
        </v-sheet>
        <v-divider></v-divider>

        <v-layout mt-4 column align-center>
          <v-list nav dense>
            <v-list-item-group
              v-model="selectedItem"
              color="deep-purple accent-4"
            >
              <v-list-item v-for="(item, i) in items" :key="i">
                <v-list-item-icon>
                  <v-icon v-text="item.icon"></v-icon>
                </v-list-item-icon>

                <v-list-item-content>
                  <router-link
                    color="error"
                    :to="{ name: item.ruta }"
                    tag="v-list-item-title"
                  >
                    <v-list-item-title v-text="item.text"></v-list-item-title>
                  </router-link>
                </v-list-item-content>
              </v-list-item>
            </v-list-item-group>
          </v-list>
        </v-layout>
      </v-navigation-drawer>
    </v-container>
  </v-app>
</template>

<script lang="ts">
import axios from 'axios'
import Vue from 'vue'
export default Vue.extend({
  
})
</script>

export default {
  data: () => ({
    step: 1,
    formAuth: {
      name: "",
      email: "",
      password: "",
      
    },
    logeado: "",
    drawer: null,
    selectedItem: 0,
    items: [
      { text: "Home", ruta: "home", icon: "mdi-folder" },
      { text: "Hello mudo", ruta: "hello", icon: "mdi-account-multiple" },
      { text: "Gestionar trabajadores", ruta: "tareas", icon: "mdi-star" },
      { text: "Gestionar gastos", ruta: "home", icon: "mdi-history" },
      { text: "Galería", ruta: "galeria", icon: "mdi-history" },
      { text: "Offline", ruta: "home", icon: "mdi-check-circle" },
      { text: "Uploads", ruta: "home", icon: "mdi-upload" },
      { text: "Backups", ruta: "home", icon: "mdi-cloud-upload" },
    ],
  }),

  beforeCreate() {
    axios
      .post("login", this.formAuth)
      .then(() => {
        this.logeado = true;
        console.log("User signed in !");
      })
      .catch(() => {
        this.logeado = false;
        console.log();
        console.log("credentials did not match");
      });
  },

  methods: {
    handleLogin() {
      const params = {
        email: this.formAuth.email,
        password: this.formAuth.password,
      };
      axios.get("/sanctum/csrf-cookie").then(() => {
        axios
          .post("login", params)
          .then(() => {
            this.logeado = true;
            console.log("User signed in !");
          })
          .catch((error) => {
            this.logeado = false;
            console.log(error);
            console.log("credentials did not match");
          }); // credentials didn't match
      });
      //console.log(this.logeado)
    },
    login() {
      const params = {
        email: this.formAuth.email,
        password: this.formAuth.password,
      };
      //console.log('hola estoy en la promesa');
      axios.get("/sanctum/csrf-cookie").then(() => {
        axios.post("login", params).then(() => {
          console.log();
        });
      });
    },

    handleRegister() {
      axios.get("/sanctum/csrf-cookie").then(() => {
        axios
          .post("register", this.formAuth)
          .then(() => {
            this.logeado = true;
            console.log("User signed in !");
          })
          .catch((error) => {
            this.logeado = false;
            console.log(error);
            console.log("credentials did not match");
          }); // credentials didn't match
      });
      //console.log(this.logeado)
    },
  },

  props: {
    source: String,
  },
};
</script>