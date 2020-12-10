<template>
  <v-card class="mt-16 py-16 px-2" dark>
    <v-card-title class="display-1 justify-center">{{ cardTitle }}</v-card-title>
    <v-spacer />
    <v-row justify="center">
      <!-- column 1 -->
      <v-col cols="12" lg="6" md="5" sm="12">
        <v-card-subtitle class="headline white--text">{{ introduction.title }}</v-card-subtitle>
        <v-card-subtitle class="title white--text">{{ introduction.subtitle }}</v-card-subtitle>
        <v-row v-for="(ability, i) in abilities" :key="i">
          <v-card elevation="0" class="ma-2">
            <v-card-title>
              <v-icon :color="ability.color" large class="py-3">{{ability.icon}}</v-icon>
            </v-card-title>
            <v-card-subtitle class="headline font-weight-medium white--text">{{ability.title}}</v-card-subtitle>
            <v-card-text class="body-2">{{ability.description}}</v-card-text>
          </v-card>
        </v-row>
      </v-col>
      <!-- column 2 -->
      <v-col cols="12" lg="4" md="5" sm="12">
        <v-card max-width="310">
          <v-avatar size="100%" class="mx-auto px-4">
            <img src="../assets/saija.png" alt="saija" class="rounded-circle" />
          </v-avatar>
          <v-card-title class="headline text-break">{{ information.name }}</v-card-title>
          <v-card-subtitle class="body-2">{{ information.title }}</v-card-subtitle>
          <v-divider class="mx-2" />
          <!-- contact info -->
          <v-card-title class="headline">{{ contactInfo }}</v-card-title>
          <v-list>
            <v-list-item v-for="(contact, i) in contacts" :key="i" class>
              <v-list-item-icon>
                <v-icon color="blue">{{ contact.icon }}</v-icon>
              </v-list-item-icon>
              <v-list-item-title class="breakline">{{ contact.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-card>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
import json from '../json/introduction.json'

export default {
  data: () => ({
    cardTitle: json.title,
    contactInfo: json.subtitle,
    introduction: json.introduction,
    abilities: json.abilities,
    contacts: json.contacts,
    information: json.information
  }),
};
</script>

<style scope>
.breakline {
  white-space: normal;
}
</style>
