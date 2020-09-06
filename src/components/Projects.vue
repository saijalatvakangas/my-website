<template>
  <v-card class="mt-16 py-16" min-height="80vh">
    <v-card-title class="display-1 d-flex justify-center">Projektit</v-card-title>
    <v-row no-gutters>
      <v-col v-for="(project, i) in projects" :key="i" cols="12" md="6" sm="12">
        <v-card class="ma-4">
          <a :href="project.website">
            <v-img :src="project.image" :aspect-ratio="16/9"></v-img>
          </a>

          <v-card-title class="headline">{{project.headline}}</v-card-title>
          <v-card-text>
            <v-chip v-for="(keyword, j) in project.keywords" :key="j" class="mr-2">{{keyword}}</v-chip>
          </v-card-text>

          <v-divider class="mx-4"></v-divider>

          <v-card-text>{{project.description}}</v-card-text>

          <v-card-actions>
            <v-btn text :href="project.website">
              <v-icon class="ma-2">mdi-home</v-icon>Kokeile
            </v-btn>

            <v-btn text :href="project.code" >
              <v-icon class="ma-2">mdi-github</v-icon>Lähdekoodi
            </v-btn>
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
        image: "https://cdn.vuetifyjs.com/images/cards/house.jpg",
        headline: "SNSReplica",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
        keywords: ["Laravel", "Vue.js"],
        website: "https://www.google.com/",
        code: "https://github.com/saijalatvakangas/snsReplica",
      },
      {
        image: "https://cdn.vuetifyjs.com/images/weather/part-cloud-48px.png",
        headline: "SNSReplica",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
        keywords: ["Laravel", "Vue.js"],
        website: "https://www.google.com/",
        code: "https://github.com/saijalatvakangas/snsReplica",
      },
    ],
  }),
};
</script>
