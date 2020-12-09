<template>
  <v-app id="inspire">
    <v-container >
      <v-app-bar app color="deep-purple accent-4" dark prominent>
        <v-app-bar-nav-icon
          class="white--text"
          @click="drawer = !drawer"
        ></v-app-bar-nav-icon>

        <v-toolbar-title >Application</v-toolbar-title>

        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-filter</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </v-app-bar>
    </v-container>
  </v-app>
</template>

<script>

export default {
}
</script>