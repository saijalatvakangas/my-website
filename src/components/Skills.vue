<template>
  <v-card class="mt-16 py-16" min-height="80vh">
    <v-card-title>Osaaminen</v-card-title>
    <v-row no-gutters>
      <v-col
        v-for="(skill, i) in skills" :key="i"
        cols="12"
        sm="6"
        md="4"
      >
      <v-card  color="#385F73" dark class="ma-2">
        <v-card-title class="headline">
          <v-icon large>
            {{skill.logo}}
          </v-icon>
        </v-card-title>

        <v-card-subtitle class="headline font-weight-bold">{{skill.headline}}</v-card-subtitle>

        <v-card-text class="font-weight-bold">
          {{skill.description}}
        </v-card-text>

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
        description: "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description: "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description: "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description: "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description: "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description: "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
      {
        logo: "mdi-twitter",
        headline: "Twitter",
        description: "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.",
      },
    ],
  }),
};
</script>
