<template>
  <v-app id="inspire">
    <v-container>
      <v-navigation-drawer v-model="drawer" temporary app>
        <v-sheet color="deep-purple accent-4" class="pa-4">
          <v-avatar class="mb-4" color="grey darken-1" size="64">
            <img src="@/assets/1.jpg" />
          </v-avatar>
          <v-btn class="badge float-right" icon @click="drawer = !drawer">
            <v-icon color="white">mdi-close</v-icon>
          </v-btn>

          <div class="white--text mt-3 headline">blhidalgo@uci</div>
        </v-sheet>
        <v-divider></v-divider>

        <v-list nav dense>
          <v-list-item link>
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>

            <v-list-item-title>Home</v-list-item-title>
          </v-list-item>

          <router-link to="materia_prima" tag="v-list-item">
            <v-list-item link>
                <v-list-item-icon>
                  <v-icon>mdi-home</v-icon>
                </v-list-item-icon>

                <v-list-item-title>Materia Prima</v-list-item-title>
            </v-list-item>
          </router-link>

          <v-list-group
            :value="false"
            no-action
            prepend-icon="mdi-account-circle"
          >
            <template v-slot:activator>
              <v-list-item-title>Producto</v-list-item-title>
            </template>
            <v-list-item v-for="([title, icon], i) in productos" :key="i" link>
              <v-list-item-title v-text="title"></v-list-item-title>
              <v-list-item-icon>
                <v-icon v-text="icon"></v-icon>
              </v-list-item-icon>
            </v-list-item>
          </v-list-group>

          <v-list-group
            :value="false"
            no-action
            prepend-icon="mdi-account-circle"
          >
            <template v-slot:activator>
              <v-list-item-title>Compra/Venta</v-list-item-title>
            </template>
            <v-list-item
              v-for="([title, icon], i) in compraventa"
              :key="i"
              link
            >
              <v-list-item-title v-text="title"></v-list-item-title>

              <v-list-item-icon>
                <v-icon v-text="icon"></v-icon>
              </v-list-item-icon>
            </v-list-item>
          </v-list-group>
        </v-list>
      </v-navigation-drawer>

      <v-app-bar app color="deep-purple accent-4" dark>
        <v-app-bar-nav-icon
          class="white--text"
          @click="drawer = !drawer"
        ></v-app-bar-nav-icon>

        <v-toolbar-title>Application</v-toolbar-title>

        <v-spacer></v-spacer>

        <div class="white--text mt-3">blhidalgo@uci</div>
        <v-btn icon>
          <v-avatar>
            <img src="@/assets/1.jpg" />
          </v-avatar>
        </v-btn>
      </v-app-bar>

      <v-main>
        <router-view />
      </v-main>
    </v-container>
  </v-app>
</template>

<script>
import axios from "axios";
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
    productos: [
      ["Listado de productos", "mdi-account-multiple-outline"],
      ["Orden", "mdi-cog-outline"],
    ],
    compraventa: [
      ["Compra", "mdi-plus-outline"],
      ["Venta", "mdi-file-outline"],
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