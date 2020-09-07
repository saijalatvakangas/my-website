<template>
  <v-card class="mt-16 py-16 px-4">
    <v-card-title class="display-1 d-flex justify-center">Koulutus</v-card-title>
    <v-timeline :dense="$vuetify.breakpoint.smAndDown">
      <v-timeline-item
        v-for="(education, i) in educations"
        :key="i"
        color="cyan darken-2"
        small
        fill-dot
      >
        <template v-slot:opposite>
          <span class="font-weight-bold">{{ education.time }}</span>
        </template>
        <v-card class="elevation-4">
          <v-card-title class="headline grey darken-4 white--text">{{ education.headline }}</v-card-title>
          <v-card-subtitle
            v-if="$vuetify.breakpoint.mdAndUp"
            class="grey darken-4 white--text"
          >{{ education.subtitle }}</v-card-subtitle>
          <v-card-subtitle v-else class="grey darken-4 white--text">{{ education.subtitle }}, {{ education.time }}</v-card-subtitle>

          <v-divider class="pb-1 cyan darken-2" />

          <v-card-text>{{ education.description }}</v-card-text>
        </v-card>
      </v-timeline-item>
    </v-timeline>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    educations: [
      {
        time: "2018 –",
        headline: "Filosofian maisteri",
        subtitle: "Jyväskylän yliopisto",
        description:
          "Pääaineeni on tietotekniikka ja suuntaavana moduulina opiskelen ohjelmisto- ja tietoliikennetekniikkaa.",
      },
      {
        time: "2019 – 2019",
        headline: "Vaihto-oppilas",
        subtitle: "Pusan National University",
        description:
          "Opiskelin neljä kuukautta Etelä-Koreassa C-ohjelmointikieltä ja kyberturvallisuutta yleisellä tasolla.",
      },
      {
        time: "2013 – 2017",
        headline: "Insinööri",
        subtitle: "Jyväskylän ammattikorkeakoulu",
        description:
          "Suoritin logistiikan koulutusohjelman, jossa pääaineenani oli materiaalinkäsittely ja varastointi. Opinnäytetyön aihe: Paloturvallisuus sisälogistiikan suunnittelussa.",
      },
      {
        time: "2008 – 2011",
        headline: "Ylioppilas",
        subtitle: "Nurmon lukio",
        description: "",
      },
    ],
  }),
};
</script>
