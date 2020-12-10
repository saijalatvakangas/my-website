<template>
  <v-card class="mt-16 py-16">
    <v-card-title class="display-1 justify-center">{{ cardTitle }}</v-card-title>
    <v-row no-gutters>
      <v-col v-for="(project, i) in projects" :key="i" cols="12" md="6" sm="12">
        <v-card class="elevation-16 ma-4">
          <!-- image is a link to project if a status is ready -->
          <a v-if="project.ready" :href="project.website">
            <v-img :src="require('../assets/' + project.image)" :aspect-ratio="16/9">
              <v-badge color="green" content="Valmis" offset-x="-2" offset-y="5"></v-badge>
            </v-img>
          </a>
          <!-- otherwise no links and an unfinished mark is added -->
          <v-img v-else :src="require('../assets/' + project.image)" :aspect-ratio="16/9">
            <v-badge color="red" content="Kehityksessä" offset-x="-2" offset-y="5"></v-badge>
          </v-img>
          <!-- project information -->
          <v-card-title class="headline">{{project.headline}}</v-card-title>
          <v-card-text>
            <v-chip v-for="(keyword, j) in project.keywords" :key="j" class="ma-1">{{keyword}}</v-chip>
          </v-card-text>
          <v-divider class="mx-4" />
          <v-card-text class="font-weight-medium">{{project.description}}</v-card-text>
          <!-- buttons -->
          <v-card-actions>
            <div v-if="project.restricted">
              <v-btn text :href="project.website">
                <v-icon class="ma-2">mdi-information</v-icon>{{ information }}
              </v-btn>
            </div>
            <div v-else class="d-flex justify-start flex-wrap">
              <v-btn v-if="project.playable" text :href="project.website">
                <v-icon class="ma-2">mdi-home</v-icon>{{ tryOut }}
              </v-btn>
              <v-btn text :href="project.code">
                <v-icon class="ma-2">mdi-github</v-icon>{{ sourceCode }}
              </v-btn>
            </div>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
import json from '../json/projects.json'

export default {
  data: () => ({
    cardTitle: json.title,
    information: json.information,
    tryOut: json.tryOut,
    sourceCode: json.sourceCode,
    projects: json.projects
  }),
};
</script>
