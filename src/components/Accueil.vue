<template>
  <v-container>
    <v-row class="text-center">
      <!--<v-col cols="12">
        <v-img
          :src="require('../assets/logo.png')"
          class="my-3"
          contain
          height="200"
        />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          OpenDay
        </h1>

        <p class="subheading font-weight-regular">
          La matinée du libre de l'Université Lumière Lyon 2
          <br>Le mercredi 3 février 2021 de 9h à 12h30
        </p>
      </v-col>

      <v-col
        class="mb-1"
        cols="12"
      >
      </v-col>-->
      <v-img
          src="../assets/open.png"
          class="my-3"
          contain
          max-height="800"/>
      <v-col class="mb-5"
      md="10" offset-md="1">
        <h2 class="headline font-weight-bold mb-3">
          Des acteurs du libre
        </h2>
        <v-row align="center"
               justify="center">
            <a href="https://framasoft.org/fr/" target="_blank">
              <v-img
                  class="ma-5"
                  alt="Framasoft Logo"
                  :src="require('../assets/framasoft.png')"
                  max-width="250"
              />
            </a>
            <a href="https://www.ploss-ra.fr/" target="_blank">
              <v-img
                  class="ma-5"
                  alt="Ploss-ra Logo"
                  :src="require('../assets/ploss-ra.png')"
                  max-width="250"
              />

            </a>
            <!--<a href="https://www.aldil.org/" target="_blank">
              <v-img
                  class="ma-5"
                  alt="Aldil Logo"
                  :src="require('../assets/ALDIL.png')"
                  max-width="250"
              />

            </a>-->
          <a href="https://www.april.org/" target="_blank">
            <v-img
                class="ma-5"
                alt="April Logo"
                :src="require('../assets/april.png')"
                max-width="250"
            />

          </a>
          <a href="https://www.oisux.org/" target="_blank">
            <v-img
                class="ma-5"
                alt="Oisux Logo"
                :src="require('../assets/oisux.png')"
                max-width="250"
            />

          </a>
          <a href="http://www.apitux.com/" target="_blank">
            <v-img
                class="ma-5"
                alt="Apitux Logo"
                :src="require('../assets/apitux.png')"
                max-width="250"
            />

          </a>
          <a href="https://www.algoo.fr/fr/" target="_blank">
            <v-img
                class="ma-5"
                alt="Algoo Logo"
                :src="require('../assets/algoo.png')"
                max-width="250"
            />

          </a>
          <a href="https://www.worteks.com/" target="_blank">
            <v-img
                class="ma-5"
                alt="April Logo"
                :src="require('../assets/worteks.png')"
                max-width="250"
            />

          </a>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({
      ecosystem: [
      ],
      importantLinks: [

      ],
    }),
  }
</script>
