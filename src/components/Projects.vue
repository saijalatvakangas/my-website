<template>
  <v-card class="mt-16 py-16">
    <v-card-title class="display-1 d-flex justify-center">Projektit</v-card-title>
    <v-row no-gutters>
      <v-col v-for="(project, i) in projects" :key="i" cols="12" md="6" sm="12">
        <v-card class="ma-4">
          <!-- image is a link to project if a status is ready -->
          <a v-if="project.ready" :href="project.website">
            <v-img :src="project.image" :aspect-ratio="16/9">
              <v-badge color="green" content="Valmis" offset-x="-2" offset-y="5"></v-badge>
            </v-img>
          </a>

          <!-- otherwise no links and an unfinished mark is added -->
          <v-img v-else :src="project.image" :aspect-ratio="16/9">
            <v-badge color="red" content="Kesken" offset-x="-2" offset-y="5"></v-badge>
          </v-img>

          <v-card-title class="headline">{{project.headline}}</v-card-title>
          <v-card-text>
            <v-chip v-for="(keyword, j) in project.keywords" :key="j" class="mr-2">{{keyword}}</v-chip>
          </v-card-text>

          <v-divider class="mx-4"></v-divider>
          <v-card-text>{{project.description}}</v-card-text>

          <!-- buttons to projects -->
          <v-card-actions>
            <div class="d-flex justify-start flex-wrap">
              <v-btn v-if="project.ready" text :href="project.website">
                <v-icon class="ma-2">mdi-home</v-icon>Kokeile
              </v-btn>

              <v-btn text :href="project.code">
                <v-icon class="ma-2">mdi-github</v-icon>Lähdekoodi
              </v-btn>
            </div>
          </v-card-actions>

        </v-card>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    projects: [
      {
        image: require("../assets/my-website.png"),
        headline: "Omat kotisivut",
        description:
          "Omat kotisivut on tehty omien taitojen ja projektien visuaalista esittämistä varten. Erityisesti tavoitteena on ollut luoda sivut, joita voi hyödyntää työnhaussa.",
        keywords: ["Vue.js", "Vuetify"],
        website: "https://www.google.com/", //TODO:päivitä
        code: "https://github.com/saijalatvakangas/my-website",
        ready: true,
      },
      {
        image: require("../assets/sl-logo2.png"),
        headline: "SNSReplica",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
        keywords: ["Laravel", "Vue.js"],
        website: "",
        code: "https://github.com/saijalatvakangas/snsReplica",
        ready: false,
      },
      {
        image: "https://cdn.vuetifyjs.com/images/weather/part-cloud-48px.png",
        headline: "Tulossa",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
        keywords: ["Laravel", "Vue.js"],
        website: "",
        code: "https://github.com/saijalatvakangas/snsReplica",
        ready: false,
      },
    ],
  }),
};
</script>
