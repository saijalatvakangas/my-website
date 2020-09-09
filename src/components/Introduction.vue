<template>
  <v-card class="mt-16 py-16 px-2" dark>
    <v-card-title class="display-1 justify-center">Esittely</v-card-title>
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
          <v-card-title class="headline">Yhteystiedot</v-card-title>
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
export default {
  data: () => ({
    introduction: {
      title: "Nimeni on Saija",
      subtitle:
        "<Opiskelen tietotekniikkaa ja olen gradua vaille valmis maisteri Jyväskylän yliopistosta. />",
    },
    abilities: [
      {
        title: "Osaaminen",
        icon: "fas fa-laptop-code",
        color: "blue",
        description:
          "Vahvin osa-alueeni front end, mutta tavoitteena on hioa itseäni full stack -kehittäjäksi.",
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

<style scope>
.breakline {
  white-space: normal;
}
</style>
