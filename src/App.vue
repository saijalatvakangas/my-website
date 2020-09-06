<template>
  <!-- App.vue -->
  <v-app id="startView" class="application">
    <NavBar />
    <v-main>
      <v-container>
        <!-- welcome card -->
        <section >
          <Welcome />
        </section>

        <!-- introduction card -->
        <section id="introduction">
          <Welcome />
        </section>


      </v-container>
    </v-main>

    <v-footer app>
      <!-- -->
    </v-footer>
  </v-app>
</template>

<script>
import NavBar from "./components/NavBar";
import Welcome from "./components/Welcome";

export default {
  name: "App",

  components: {
    NavBar,
    Welcome,
  },

  data: () => ({
    //
  }),
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Nunito');

.application {
  font-family: 'Nunito';
}
</style>
