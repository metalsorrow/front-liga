<template>
  <div class="Presentacion">
    <v-carousel
      cycle
      height="400"
      hide-delimiter-background
      show-arrows-on-hover
    >
      <v-carousel-item v-for="(slide, i) in slides" :key="i">
        <v-sheet :color="colors[i]" height="100%">
          <v-row class="fill-height" align="center" justify="center">
            <div class="display-3">{{ slide }} Slide</div>
          </v-row>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>

    <v-container :key="align" class="grey lighten-5 mb-6">
      <!-- Cards Title -->
      <v-row no-gutters class="d-flex justify-center ma-10">
        <h2 class="text-center">
          Revisa los resultados en el menor tiempo Posible!
        </h2>
        <p>
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ad alias
          distinctio eum earum doloremque vel dolores voluptatem. Minima
          adipisci assumenda quae fugiat eaque optio animi earum unde.
          Cupiditate, optio consequatur.
        </p>
      </v-row>
      <!-- Cards -->
      <v-row no-gutters>
        <v-col v-for="card in cards" :key="card.id" style="margin: 1rem">
          <CardCustomMain :card="card"> </CardCustomMain>
        </v-col>
      </v-row>
    </v-container>
    <v-container>
      <v-row class="d-flex justify-center ma-10">
        <h2 class="text-center">
          Inscribete en nuestro sistema de campeonatos
        </h2>
        <p>No te quedes fuera!</p>
      </v-row>
      <v-row>
        <v-col>
          <v-row justify="center">
            <v-expansion-panels accordion>
              <v-expansion-panel v-for="(item, i) in 5" :key="i">
                <v-expansion-panel-header>Item</v-expansion-panel-header>
                <v-expansion-panel-content>
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed
                  do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                  Ut enim ad minim veniam, quis nostrud exercitation ullamco
                  laboris nisi ut aliquip ex ea commodo consequat.
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-row>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-card class="mx-auto" max-width="400">
            <v-toolbar color="purple" dark>
              <v-app-bar-nav-icon></v-app-bar-nav-icon>

              <v-toolbar-title>Settings</v-toolbar-title>

              <v-spacer></v-spacer>

              <v-btn icon>
                <v-icon>mdi-magnify</v-icon>
              </v-btn>
            </v-toolbar>

            <v-list subheader three-line>
              <v-subheader>User Controls</v-subheader>

              <v-list-item>
                <v-list-item-content>
                  <v-list-item-title>Content filtering</v-list-item-title>
                  <v-list-item-subtitle
                    >Set the content filtering level to restrict appts that can
                    be downloaded</v-list-item-subtitle
                  >
                </v-list-item-content>
              </v-list-item>

              <v-list-item>
                <v-list-item-content>
                  <v-list-item-title>Password</v-list-item-title>
                  <v-list-item-subtitle
                    >Require password for purchase or use password to restrict
                    purchase</v-list-item-subtitle
                  >
                </v-list-item-content>
              </v-list-item>
            </v-list>

            <v-divider></v-divider>

            <v-list flat subheader three-line>
              <v-subheader>General</v-subheader>

              <v-list-item-group v-model="settings" multiple active-class="">
                <v-list-item>
                  <template v-slot:default="{ active }">
                    <v-list-item-action>
                      <v-checkbox :input-value="active"></v-checkbox>
                    </v-list-item-action>

                    <v-list-item-content>
                      <v-list-item-title>Notifications</v-list-item-title>
                      <v-list-item-subtitle
                        >Notify me about updates to apps or games that I
                        downloaded</v-list-item-subtitle
                      >
                    </v-list-item-content>
                  </template>
                </v-list-item>

                <v-list-item>
                  <template v-slot:default="{ active }">
                    <v-list-item-action>
                      <v-checkbox :input-value="active"></v-checkbox>
                    </v-list-item-action>

                    <v-list-item-content>
                      <v-list-item-title>Sound</v-list-item-title>
                      <v-list-item-subtitle
                        >Auto-update apps at any time. Data charges may
                        apply</v-list-item-subtitle
                      >
                    </v-list-item-content>
                  </template>
                </v-list-item>

                <v-list-item>
                  <template v-slot:default="{ active }">
                    <v-list-item-action>
                      <v-checkbox :input-value="active"></v-checkbox>
                    </v-list-item-action>

                    <v-list-item-content>
                      <v-list-item-title>Auto-add widgets</v-list-item-title>
                      <v-list-item-subtitle
                        >Automatically add home screen widgets when downloads
                        complete</v-list-item-subtitle
                      >
                    </v-list-item-content>
                  </template>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-card>
        </v-col>
        <v-col>
          <v-card class="mx-auto" max-width="300" tile>
            <v-list dense>
              <v-subheader>REPORTS</v-subheader>
              <v-list-item-group v-model="selectedItem" color="primary">
                <v-list-item v-for="(item, i) in items" :key="i">
                  <v-list-item-icon>
                    <v-icon v-text="item.icon"></v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title v-text="item.text"></v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
// // @ is an alias to /src
// import PresentacionPage from "@/components/PresentacionPage.vue";
import CardCustomMain from "@/components/CardCustomMain.vue";

export default {
  name: "Presentacion",
  data() {
    return {
      //Slider
      colors: [
        "indigo",
        "warning",
        "pink darken-2",
        "red lighten-1",
        "deep-purple accent-4"
      ],
      slides: ["First", "Second", "Third", "Fourth", "Fifth"],
      
      //list
      settings: [],
      
      //list2
      selectedItem: 1,
      items: [
        { text: 'Real-Time', icon: 'mdi-clock' },
        { text: 'Audience', icon: 'mdi-account' },
        { text: 'Conversions', icon: 'mdi-flag' },
      ],
      
      //cards
      cards: [
        { id: 1, desc: "item 1" },
        { id: 2, desc: "item 2" },
        { id: 3, desc: "item 3" },
        { id: 4, desc: "item 4" }
      ]
    };
  },
  components: { CardCustomMain }
};
</script>
