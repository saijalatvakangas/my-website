<template>
  <v-card class="d-flex flex-column justify-start justify-sm-center mt-16 py-16" min-height="80vh">
    <div class="centering">
      <v-img src="../assets/sl-logo2.png" max-height="100" max-width="100" />
    </div>
    <v-card-title class="text-h4 text-sm-h2 centering">Saija Latvakangas</v-card-title>
    <v-card-actions class="centering flex-wrap">
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
        target: "#skills",
        name: "Osaaminen",
      },
      {
        target: "#education",
        name: "Koulutus",
      },
      {
        target: "#workExperience",
        name: "Työkokemus",
      },
      {
        target: "#projects",
        name: "Projektit",
      },
    ],
  }),
};
</script>

<style scope>
.centering{
  display: flex;
  justify-content: center;
}
</style>
