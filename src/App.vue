<template>
  <v-app id="startView" class="application">
    <NavBar />
    <v-main class="grey lighten-4">
      <v-container>
        <section>
          <Welcome />
        </section>

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
