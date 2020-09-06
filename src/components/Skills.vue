<template>
  <v-card class="mt-16 py-16" min-height="80vh">
    <v-card-title class="display-1 d-flex justify-center">Osaaminen</v-card-title>
    <v-row no-gutters>
      <v-col v-for="(skill, i) in skills" :key="i" cols="12" md="4" sm="6">
        <v-card elevation="0" class="ma-2">
          <v-card-title>
            <v-icon large class="py-3" color="deep-purple lighten-1">{{skill.logo}}</v-icon>
          </v-card-title>

          <v-card-subtitle class="headline font-weight-medium black--text">{{skill.headline}}</v-card-subtitle>

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
        logo: "mdi-twitter",
        headline: "Twitter",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description:
          "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
    ],
  }),
};
</script>
