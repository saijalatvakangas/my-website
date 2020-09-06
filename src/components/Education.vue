<template>
  <v-card class="mt-16 py-16 px-4" min-height="80vh">
    <v-card-title class="display-1 d-flex justify-center">Koulutus</v-card-title>
    <v-timeline :dense="$vuetify.breakpoint.smAndDown">
      <v-timeline-item v-for="(education, i) in educations" :key="i" color="cyan" large>
        <template v-slot:opposite>
          <span>{{ education.time }}</span>
        </template>
        <v-card class="elevation-2">
          <v-card-title class="headline">{{ education.headline }}</v-card-title>
          <v-card-subtitle v-if="$vuetify.breakpoint.smAndDown">{{ education.time }}</v-card-subtitle>
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
        time: "2018–",
        headline: "Jyväskylän yliopisto",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        time: "2013–2017",
        headline: "Twitter",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
    ],
  }),
};
</script>
