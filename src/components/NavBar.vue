<template>
  <div>
    <!-- an upper navigation bar -->
    <v-app-bar
      :collapse="!collapseOnScroll"
      :collapse-on-scroll="collapseOnScroll"
      absolute
      color="#bfada5"
      dark
      scroll-target="#scrolling-techniques-6"
    >
      <v-app-bar-nav-icon @click="drawer=!drawer" />
      <v-toolbar-title class="title">Saija Latvakangas</v-toolbar-title>

      <v-spacer />

      <v-toolbar-title>
        <v-btn
          v-for="media in socialMedias"
          :key="media"
          :href="media.url"
          class="mx-1 pa-5 brown lighten-4"
          small
          icon
        >
          <v-icon>{{media.icon}}</v-icon>
        </v-btn>
      </v-toolbar-title>
    </v-app-bar>

    <!-- a side drawer -->
    <v-navigation-drawer v-model="drawer" absolute temporary color="#d8ebf1" :width="320">
      <v-list>
        <v-list-item>
          <v-list-item-avatar size="62">
            <v-img src="../assets/saija.png"></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title class="title">Saija Latvakangas</v-list-item-title>
            <v-list-item-subtitle>Tietotekniikan maisteriopiskelija</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-list>

      <v-divider class="ml-3 mr-3 lightPurple" />

      <!-- a contacts list -->
      <v-list>
        <v-list-item v-for="contact in contacts" :key="contact.title" class="mb-n4">
          <v-list-item-icon>
            <v-icon class="pa-2 mr-n4 lightPurple rounded-circle" color="white">{{ contact.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ contact.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <!-- socialmedia contacts -->
        <v-list-item
          v-for="media in socialMedias"
          :key="media.title"
          class="mb-n4"
          link
          :href="media.url"
        >
          <v-list-item-icon>
            <v-icon class="pa-2 mr-n4 lightPurple rounded-circle" color="white">{{ media.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ media.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
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
        url: "https://www.linkedin.com/",
        title: "LinkedIn",
      },
      {
        icon: "mdi-github",
        url: "https://github.com/saijalatvakangas/",
        title: "GitHub",
      },
    ],
    contacts: [
      {
        title: "saijalatvakangas@gmail.com",
        icon: "mdi-email",
      },
      {
        title: "+358 40 8377173",
        icon: "mdi-cellphone",
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
