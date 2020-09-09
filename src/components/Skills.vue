<template>
  <v-card class="mt-16 py-16">
    <v-card-title class="display-1 justify-center">Osaaminen</v-card-title>
    <v-row no-gutters>
      <v-col v-for="(skill, i) in skills" :key="i" cols="12" md="4" sm="6">
        <v-card elevation="0" class="ma-2">
          <v-card-title>
            <v-icon large class="py-3" :color="skill.color">{{skill.logo}}</v-icon>
          </v-card-title>
          <v-card-subtitle class="headline font-weight-medium black--text">
            {{skill.headline}}
            <v-rating
              class="ml-n2"
              v-model="skill.rating"
              small
              color="orange"
              background-color="orange lighten-3"
            />
          </v-card-subtitle>
          <v-card-text class="font-weight-bold">{{skill.description}}</v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    skills: [
      {
        logo: "fab fa-js-square",
        headline: "JavaScript",
        color: "#FFD600",
        rating: 4,
        description:
          "JavaScript on vahvin ohjelmointikieleni, jota on tullut käytettyä sekä yliopiston kursseilla että pienissä vapaa-ajan projekteissa.",
      },
      {
        logo: "fab fa-laravel",
        headline: "Laravel",
        color: "#F44336",
        rating: 3,
        description:
          "Laravel on yksi uusimmista taidoistani, joita olen opiskellut vapaa-ajalla. Ohjelmointikielen taidot ovat hyvät, mutta kehitettävää löytyy, jotta työhön tulee kokemuksen tuomaa varmuutta.",
      },
      {
        logo: "fab fa-vuejs",
        headline: "Vue.js",
        color: "#43A047",
        rating: 3,
        description:
          "Vue.js on toinen uusimmista ohjelmontikielistäni, jota olen opiskellut vapaa-ajalla mm. näiden kotisivujen tekemiseen. Taitoni ovat hyvät, mutta vähäisen kokemuksen takia myös kehitettävää löytyy.",
      },
      {
        logo: "fab fa-react",
        headline: "React",
        color: "#40C4FF",
        rating: 2,
        description:
          "Reactista minulla on perusteet ja olen käyttänyt ohjelmointikieltä yliopiston kurssilla ja projekteissa sovelluksien kehittämiseen.",
      },
      {
        logo: "fab fa-java",
        headline: "Java",
        color: "#F44336",
        rating: 2,
        description:
          "Javasta minulla on perusteet. Ohjelmointikurssilla olen kehittänyt frisbeegolffiin tarkoitetun kirjanpitosovelluksen.",
      },
      {
        logo: "mdi-language-csharp",
        headline: "C#",
        color: "#1565C0",
        rating: 1,
        description:
          "C#:sta minulla on alkeet ja ohjelmointikussilla olen tehnyt pelin. ",
      },
      {
        logo: "fab fa-gitkraken",
        headline: "Versiohallinta / GitKraken",
        color: "#00897B",
        rating: 4,
        description:
          "Versiohallinnan käytänteitä olen opettellut vapaa-ajalla omissa sovelluksissa sekä pienissä tiimeissä sovelluskehitysprojekteissa. Versionhallinta onnistuu komentoriviltä ja graafisella käyttöliittymällä (GitKraken).",
      },
      {
        logo: "fab fa-ubuntu",
        headline: "Ubuntu",
        color: "#E65100",
        rating: 4,
        description:
          "Ubuntu-käyttöjärjestelmä on tuttu graafisella tasolla, mutta terminaalityöskentely onnistuu myös. Lisäksi kokemusta löytyy Linux-virtuaalipalvelimen ylläpidosta kurssiprojektin myötä.",
      },
      {
        logo: "fab fa-windows",
        headline: "Windows",
        color: "#00B0FF",
        rating: 4,
        description:
          "Windows on ollut elämänkumppani viimeiset 15 vuotta ja komentoriviä on tullut myös vähän käytettyä.",
      },
    ],
  }),
};
</script>
