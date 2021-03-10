<template>
  <v-app>
    <v-app-bar
      app
      dark
    >
      <div class="d-flex align-left">
        <v-app-bar-nav-icon @click="drawer = true">
        </v-app-bar-nav-icon>
      </div>
      <v-spacer></v-spacer>
      <div class="d-flex align-right">
        <router-link to="/" >
        <v-img
          alt="OpenDay Logo"
          contain
          :src="require('./assets/logo.png')"
          transition="scale-transition"
          width="40"
        />
        </router-link>
      </div>


      
    </v-app-bar>
    <v-navigation-drawer
        v-model="drawer"
        absolute
        temporary
    >
      <v-list
          nav
          dense
      >
        <v-list-item-group
            v-model="group"
            active-class="deep-purple--text text--accent-4"
        >
          <router-link to="/" tag="v-list-item" >
              <v-list-item>
                <v-list-item-icon>
                  <v-icon>mdi-home</v-icon>
                </v-list-item-icon>
                <v-list-item-title>Accueil </v-list-item-title>
              </v-list-item>
          </router-link>

          <router-link to="/Inscription" tag="v-list-item" >
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-account</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Inscription</v-list-item-title>
            </v-list-item>
          </router-link>

          <router-link to="/Planning" tag="v-list-item" >
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-calendar-clock</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Conférences</v-list-item-title>
            </v-list-item>
          </router-link>

          <!--<router-link to="/" tag="v-list-item" >
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-event</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Quizz</v-list-item-title>
            </v-list-item>
          </router-link>

          <router-link to="/" tag="v-list-item" >
          <v-list-item>


            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Contact</v-list-item-title>

          </v-list-item>
          </router-link>-->
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <router-view></router-view>
    </v-main>
    <v-footer
        :padless="padless"
    >
      <v-col
          class="text-center"
          cols="12"
      >
        {{ new Date().getFullYear() }} — <strong>Développé avec Vuetify</strong><br/>
        Code disponible sur <a href="https://github.com/QuVil/openday-website" target="_blank">GitHub</a>
      </v-col>
    </v-footer>
  </v-app>

</template>

<script>
import Vue from 'vue';
import VueRouter from 'vue-router';
import HelloWorld from './components/Accueil';
import Planning from "./components/Planning";
import Inscription from "./components/Inscription";
import ValidateInsc from "./components/ValidateInsc";

Vue.use(VueRouter);
// Defining the routes
const routes = [
  { path: '/', component: HelloWorld },
  { path: '/Planning', component: Planning },
  {path: '/Inscription', component: Inscription},
  {path: '/validate', component: ValidateInsc}
];
// Creating the router
const router = new VueRouter({ routes });

export default {
  router,
  name: 'App',



  data: () => ({
    drawer: false,
    group: null,
  }),
};
</script>
