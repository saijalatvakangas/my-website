<template>
  <v-app-bar
    :collapse="!collapseOnScroll"
    :collapse-on-scroll="collapseOnScroll"
    fixed
    dark
  >
    <!-- a logo -->
    <v-btn color="transparent" icon class="mx-2" @click="$vuetify.goTo('#startView')">
      <v-img src="../assets/logo-white.png" max-height="45" max-width="45" class="mx-2" />
    </v-btn>
    <v-spacer />
    <!-- social media icons, hides on scroll -->
    <v-toolbar-title>
      <v-btn v-for="(media, i) in socialMedias" :key="i" :href="media.url" class="pa-5" large icon>
        <v-icon>{{media.icon}}</v-icon>
      </v-btn>
    </v-toolbar-title>
  </v-app-bar>
</template>

<script>
import json from '../json/navbar.json'

export default {
  data: () => ({
    collapseOnScroll: true,
    socialMedias: json.socialMedias
  }),
};
</script>
