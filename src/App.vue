<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>
  
      <v-btn
        to="/"
        text
      >
        <span class="mr-2">
          Pagina Principal
        </span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
      
      <v-btn
        to="liga"
        text
      >
        <span class="mr-2">
          Liga
        </span>
        <v-icon>mdi-soccer</v-icon>
      </v-btn>
  
      <v-btn
        to="/campeonatos"
        text
      >
        <span class="mr-2">
          Campeonatos
        </span>
        <v-icon>mdi-cards-diamond</v-icon>
      </v-btn>

      <v-btn
        to="/equipo"
        text
      >
        <span class="mr-2">
          Equipo
        </span>
        <v-icon>mdi-account-multiple</v-icon>
      </v-btn>
      
      <v-btn
        to="hello"
        text
      >
        <span class="mr-2">
          Hello!
        </span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>
    <FooterCustomMain>
    </FooterCustomMain>
  </v-app>
</template>

<script>

import FooterCustomMain from '@/components/FooterCustomMain.vue'

export default {
  name: "App",

  components: {
    FooterCustomMain
  },

  data: () => ({
    //
  })
};
</script>
