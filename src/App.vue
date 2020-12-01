<template>
<v-app>
  <AppBar></AppBar>
  <v-container class="white lighten-4" fill-height fluid>
    <v-layout row wrap class="align-content-center">
      <v-flex xs12>
        
        <Home/>
      </v-flex>
    </v-layout>
  </v-container>
</v-app>
</template>

<script>
import Home from "./components/Main.vue"
import AppBar from "./components/appBar.vue"

export default {
  components: {
    Home,
    AppBar
  }
}
</script>
