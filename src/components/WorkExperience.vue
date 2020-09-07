<template>
  <v-card class="mt-16 py-16 px-4">
    <v-card-title class="display-1 d-flex justify-center">Työkokemus</v-card-title>
    <v-card-subtitle class="body-2 font-weight-medium mt-4">{{ info }}</v-card-subtitle>
    <v-timeline :dense="$vuetify.breakpoint.smAndDown">
      <v-timeline-item v-for="(experience, i) in experiences" :key="i" color="orange darken-4" small fill-dot>
        <template v-slot:opposite>
          <span class="font-weight-bold">{{ experience.time }}</span>
        </template>
        <v-card class="elevation-4">
          <v-card-title class="headline grey darken-4 white--text">{{ experience.position }}</v-card-title>
          <v-card-subtitle
            v-if="$vuetify.breakpoint.mdAndUp"
            class="grey darken-4 white--text"
          >{{ experience.employer }}</v-card-subtitle>
          <v-card-subtitle v-else class="grey darken-4 white--text">{{ experience.employer }}, {{ experience.time }}</v-card-subtitle>
          <v-card-subtitle v-if="$vuetify.breakpoint.smAndDown">{{ experience.time }}</v-card-subtitle>

          <v-divider class="pb-1 orange darken-4" />

          <v-card-text>{{ experience.description }}</v-card-text>
        </v-card>
      </v-timeline-item>
    </v-timeline>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    info: "Työkokemusta löytyy reilu neljä vuotta, josta ohjelmistokehityksen osuus on melkein vuosi. Alle on listattu neljä viimeisintä työtäni. Lisää tietoja aiemmista töistä voi kysellä joko sähköpostitse tai puhelimitse.",
    experiences: [
      {
        time: "02/2020 – 06/2020",
        position: "Projektipäällikkö",
        employer: "Thinking Lifeline Oy",
        description: "Osallistuin sovelluskehitysprojektiin, jossa työskentelin osana 5 hlön projektiryhmää. Vastuullani oli projektin suunnittelu ja läpivienti sekä projektin sisäinen ja ulkoinen viestintä. Vastasin myös ohjelmiston testaamisesta.",
      },
      {
        time: "11/2018 – 05/2019",
        position: "Tutkimusavustaja",
        employer: "Jyväskylän yliopisto",
        description: "Työskentelin IoT:sta uutta liiketoimintaa -hankkeessa osana 5-8 hlön projektiryhmää. Osallistuin IoT-laitteiden kokoamiseen ja asentamiseen. Kehitettävään sovellukseen opiskelin Reactia. Lisäksi osallistuin palvelimen konfigurointiin.",
      },
      {
        time: "Kesät 2015 – 2017",
        position: "Logistiikkatyöntekijä",
        employer: "A-Logistiikka Oy",
        description: "Keräsin automaattivarastosta tulevia asiakastilauksia omalla työpisteellä. Opettelin varastohallintajärjestelmän virheiden korjaamisen asetuksista, mikä nopeutti työskentelyä ja pystyin auttamaan muita samojen ongelmien kanssa.",
      },
      {
        time: "Kesät 2011 ja 2014",
        position: "Pakkaaja",
        employer: "Atria-Chick Oy",
        description: "Toimin kanatuotteiden pakkaajana, mutta tein myös konemiesten töitä. Työpisteillä yritin ottaa päävastuun ja hoitaa teknisiä ongelmatilanteita.",
      },
    ],
  }),
};
</script>
