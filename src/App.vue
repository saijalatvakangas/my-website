<template>
  <!-- App.vue -->
  <v-app id="startView" class="application">
    <NavBar />
    <v-main>
      <v-container>
        <!-- welcome card -->
        <section>
          <Welcome />
        </section>

        <!-- introduction card -->
        <section id="introduction">
          <Introduction />
        </section>

        <section id="skills">
          <Skills />
        </section>

        <section id="education">
          <Education />
        </section>

        <section id="workExperience">
          <WorkExperience />
        </section>

        <section id="projects">
          <Projects />
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
import Introduction from "./components/Introduction";
import Skills from "./components/Skills";
import Education from "./components/Education";
import WorkExperience from "./components/WorkExperience";
import Projects from "./components/Projects";

export default {
  name: "App",

  components: {
    NavBar,
    Welcome,
    Introduction,
    Skills,
    Education,
    WorkExperience,
    Projects,
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
