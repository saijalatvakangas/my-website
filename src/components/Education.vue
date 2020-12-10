<template>
  <v-card class="mt-16 py-16 px-4">
    <v-card-title class="display-1 d-flex justify-center">{{ cardTitle }}</v-card-title>
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
          <v-card-title
            class="text-h6 text-sm-h5 grey darken-4 white--text text-break"
          >{{ education.headline }}</v-card-title>
          <v-card-subtitle
            v-if="$vuetify.breakpoint.mdAndUp"
            class="grey darken-4 white--text"
          >{{ education.subtitle }}</v-card-subtitle>
          <v-card-subtitle
            v-else
            class="grey darken-4 white--text"
          >{{ education.subtitle }}, {{ education.time }}</v-card-subtitle>
          <v-divider class="pb-1 cyan darken-2" />
          <v-card-text class="font-weight-medium">{{ education.description }}</v-card-text>
        </v-card>
      </v-timeline-item>
    </v-timeline>
  </v-card>
</template>

<script>
import json from '../json/education.json'

export default {
  data: () => ({
    cardTitle: json.title,
    educations: json.educations
  }),
};
</script>
