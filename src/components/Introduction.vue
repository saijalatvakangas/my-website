<template>
  <v-card class="mt-16 py-16 px-6" dark>
    <v-card-title class="display-1 d-flex justify-center">Esittely</v-card-title>
    <v-spacer />
    <v-row justify="center">
      <!-- column 1 -->
      <v-col cols="12" md="6" sm="11">
        <v-card-subtitle class="headline white--text">{{ introduction.title }}</v-card-subtitle>
        <v-card-subtitle class="title white--text">{{ introduction.subtitle }}</v-card-subtitle>
        <v-row v-for="(ability, i) in abilities" :key="i">
          <v-card elevation="0" class="ma-2">
            <v-card-title>
              <v-icon  :color="ability.color" large class="py-3">{{ability.icon}}</v-icon>
            </v-card-title>

            <v-card-subtitle class="headline font-weight-medium white--text">{{ability.title}}</v-card-subtitle>
            <v-card-text class="body-2">{{ability.description}}</v-card-text>
          </v-card>
        </v-row>
      </v-col>

      <!-- column 2 -->
      <v-col cols="12" md="4" sm="11">
        <v-card max-width="310" min-width="300">
          <v-avatar size="270" class="ma-4">
            <img src="../assets/saija2.png" alt="saija" class="rounded-circle"/>
          </v-avatar>
          <v-card-title class="headline">{{ information.name }}</v-card-title>
          <v-card-subtitle class="body-2">{{ information.title }}</v-card-subtitle>

          <v-divider class="mx-2"></v-divider>

          <!-- contact info -->
          <v-card-title class="headline">Yhteystiedot</v-card-title>
          <v-list>
            <v-list-item v-for="(contact, i) in contacts" :key="i" class="my-n3">
              <v-list-item-icon>
                <v-icon color="blue">{{ contact.icon }}</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title>{{ contact.title }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-card>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    introduction: {
      title: "Nimeni on Saija",
      subtitle: "<Olen gradua vaille valmis maisteri Jyväskylän yliopistosta. />",
    },
    abilities: [
      {
        title: "Osaaminen",
        icon: "fas fa-laptop-code",
        color: "blue",
        description:
          "Pääaineeni on tietotekniikka ja vahvin osa-alueeni front end, mutta tavoitteena on hioa itseäni full stack -kehittäjäksi.",
      },
      {
        title: "Vahvuuteni",
        icon: "fas fa-award",
        color: "yellow",
        description:
          "Olen suhteellisen tuore koodari, joka ei ole vakiintunut liikaa yhteen ohjelmointikieleen, joten olen varsin muuntautumiskykyinen.",
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
      {
        title: "Jyväskylä",
        icon: "mdi-map-marker",
      },
    ],
    information: {
      name: "Saija Latvakangas",
      title: "Tietotekniikan maisteriopiskelija",
    },
  }),
};
</script>
