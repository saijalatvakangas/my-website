<template>
  <div>
    <!-- an upper navigation bar -->
    <v-app-bar
      :collapse="!collapseOnScroll"
      :collapse-on-scroll="collapseOnScroll"
      absolute
      color="#222222"
      dark
      scroll-target="#scrolling-techniques-6"
    >
      <!-- <v-app-bar-nav-icon @click="drawer=!drawer" /> -->
      <v-btn color="transparent" icon class="mx-2">
        <v-img src="../assets/sl-logo1.png" max-height="45" max-width="45" class="mx-2 " />
      </v-btn>
      <!-- <v-toolbar-title class="title">Saija Latvakangas</v-toolbar-title> -->

      <v-spacer />

      <v-toolbar-title>
        <v-btn
          v-for="media in socialMedias"
          :key="media.title"
          :href="media.url"
          class=" pa-5"
          large
          icon
        >
          <v-icon>{{media.icon}}</v-icon>
        </v-btn>
      </v-toolbar-title>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  data: () => ({
    collapseOnScroll: true,
    drawer: false,
    socialMedias: [
      {
        icon: "mdi-linkedin",
        url: "https://www.linkedin.com/in/saija-latvakangas-219b931b4/",
        title: "LinkedIn",
      },
      {
        icon: "mdi-github",
        url: "https://github.com/saijalatvakangas/",
        title: "GitHub",
      },
    ],
  }),
};
</script>

<style scoped>
.lightPurple {
  background-color: #5b5c79;
}
</style>
