<template>
  <v-app>
    <NavBar />
    <HomePage />
    <ComponentFooter />
  </v-app>
</template>

<script>
import HomePage from "./views/HomePage.vue";
import NavBar from "./components/NavBar.vue";
import ComponentFooter from "./components/ComponentFooter.vue";
export default {
  name: "App",
  components: {
    HomePage,
    NavBar,
    ComponentFooter,
  },
};
</script>

<style scoped>
*{
font-family: 'Be Vietnam Pro', sans-serif;
}



</style>
