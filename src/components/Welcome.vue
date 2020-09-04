<template>
  <v-card class="d-flex flex-column justify-start justify-sm-center mt-16 py-16" min-height="80vh">
    <v-card-title class="text-h4 text-sm-h2 d-flex justify-center">Saija Latvakangas</v-card-title>
    <v-card-actions class="d-flex flex-wrap justify-center">
      <v-btn
        v-for="(button, i) in buttons"
        :key="i"
        text
        @click="$vuetify.goTo(button.target)"
      >{{button.name}}
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    buttons: [
      {
        target: "#introduction",
        name: "Esittely",
      },
      {
        target: "#introduction",
        name: "Osaaminen",
      },
      {
        target: "#introduction",
        name: "Koulutus",
      },
      {
        target: "#introduction",
        name: "Työkokemus",
      },
      {
        target: "#introduction",
        name: "Projektit",
      },
    ],
  }),
};
</script>
