<template>
  <v-card class="mt-16 py-16">
    <v-card-title class="display-1 justify-center">{{ cardTitle }}</v-card-title>
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
import json from '../json/skills.json'

export default {
  data: () => ({
    cardTitle: json.title,
    skills: json.skills
  }),
};
</script>
