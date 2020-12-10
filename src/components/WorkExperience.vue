<template>
  <v-card class="mt-16 py-16 px-4">
    <v-card-title class="display-1 justify-center">{{ cardTitle }}</v-card-title>
    <v-card-subtitle class="body-2 font-weight-medium mt-4">{{ info }}</v-card-subtitle>
    <v-timeline :dense="$vuetify.breakpoint.smAndDown">
      <v-timeline-item
        v-for="(job, i) in jobs"
        :key="i"
        color="orange darken-4"
        small
        fill-dot
      >
        <template v-slot:opposite>
          <span class="font-weight-bold">{{ job.time }}</span>
        </template>
        <v-card class="elevation-4">
          <v-card-title
            class="text-h6 text-sm-h5 grey darken-4 white--text text-break"
          >{{ job.position }}</v-card-title>
          <v-card-subtitle
            v-if="$vuetify.breakpoint.mdAndUp"
            class="grey darken-4 white--text"
          >{{ job.employer }}</v-card-subtitle>
          <v-card-subtitle
            v-else
            class="grey darken-4 white--text"
          >{{ job.employer }}, {{ job.time }}</v-card-subtitle>
          <v-divider class="pb-1 orange darken-4" />
          <v-card-text class="font-weight-medium">{{ job.description }}</v-card-text>
        </v-card>
      </v-timeline-item>
    </v-timeline>
  </v-card>
</template>

<script>
import json from '../json/experience.json'

export default {
  data: () => ({
    cardTitle: json.title,
    info: json.info,
    jobs: json.experience
  }),
};
</script>
