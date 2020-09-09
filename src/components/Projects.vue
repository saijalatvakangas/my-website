<template>
  <v-card class="mt-16 py-16">
    <v-card-title class="display-1 justify-center">Projektit</v-card-title>
    <v-row no-gutters>
      <v-col v-for="(project, i) in projects" :key="i" cols="12" md="6" sm="12">
        <v-card class="elevation-16 ma-4">
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
          <!-- project information -->
          <v-card-title class="headline">{{project.headline}}</v-card-title>
          <v-card-text>
            <v-chip v-for="(keyword, j) in project.keywords" :key="j" class="ma-1">{{keyword}}</v-chip>
          </v-card-text>
          <v-divider class="mx-4" />
          <v-card-text class="font-weight-medium">{{project.description}}</v-card-text>
          <!-- buttons -->
          <v-card-actions>
            <div v-if="project.restricted">
              <v-btn text :href="project.website">
                <v-icon class="ma-2">mdi-information</v-icon>Tietoja
              </v-btn>
            </div>
            <div v-else class="d-flex justify-start flex-wrap">
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
        keywords: ["Vue.js", "Vuetify", "Yksilötyö"],
        website: "#startView",
        code: "https://github.com/saijalatvakangas/my-website",
        ready: true,
        restricted: false,
      },
      {
        image: require("../assets/protomyy.png"),
        headline: "Protomyy-projekti (NDA)",
        description:
          "Yritykselle tehty projekti, jossa toteutettiin hoivarobottiin prototyypit puheentunnistuksesta ja Android-tabletin kautta käytettävästä vanhuksen käyttöliittymästä.",
        keywords: ["React Native", "C++", "Python", "Ryhmätyö"],
        website: "http://www.mit.jyu.fi/palvelut/sovellusprojektit/protomyy/",
        code: "",
        ready: true,
        restricted: true,
      },
      {
        image: require("../assets/sns-replica.png"),
        headline: "SNSReplica",
        description:
          "Sosiaalisen median jäljitelmä, johon on käytetty pohjana Youtube-tutoriaalia. Tavoitteena on ollut tutustua Laraveliin.",
        keywords: ["Laravel", "Yksilötyö"],
        website: "",
        code: "https://github.com/saijalatvakangas/snsReplica",
        ready: true,
        restricted: false,
      },
      {
        image: require("../assets/math-me-up.png"),
        headline: "Math Me Up!",
        description:
          "Laskutaitoon pohjautuva peli, jossa tulee vastata kysymyksiin oikein mahdollisimman nopeasti. Tavoitteena tutustua Laraveliin ja backendiin syvemmin.",
        keywords: ["Laravel", "Vue.js", "Parityö"],
        website: "",
        code: "https://github.com/saijalatvakangas/mathMeUp",
        ready: false,
        restricted: false,
      },
    ],
  }),
};
</script>
