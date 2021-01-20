<template>
  <v-container>
<!--    <v-row class="text-center">-->
<!--      <v-col cols="12">-->
<!--        Inscription obligatoire pour participer à l'événement.<br>-->
<!--        Fermeture des inscrption le dimanche 31 janvier.<br>-->
<!--        Les adresses mails seront seulement utilisées pour vous envoyer le lien de la plateforme de visioconférence quelques jours avant l'événement.-->
<!--        Toutes les données enregistrées seront supprimées après l'événement.-->

<!--      </v-col>-->
<!--    </v-row>-->
    <div id="insc-text">
      <v-card :loading="loading" class="mx-auto my-12">
        <template slot="progress">
          <v-progress-linear
              color="deep-purple"
              height="10"
              indeterminate
          ></v-progress-linear>
        </template>

        <v-card-title>Procédure d'inscription</v-card-title>
        <v-card-text>
          <div>
            L'inscription est obligatoire pour participer à l'événement. La fermeture des inscription est prévue pour le 1er février 2021.<br/>
            Votre adresse mail sera uniquement utilisée pour vous envoyer le lien de la plate-forme de visio-conférence quelques jours avant l'événement.<br/>
            Toutes les données enregistrées seront supprimées dès la fin des conférences.
          </div>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>

        <v-card-actions class="justify-center">
          <v-btn
              class="mr-4"
              large
              color="success"
              @click="insc"
              href='https://framaforms.org/inscription-openday-1611136545-0'
          >
            S'inscrire à l'OpenDay
          </v-btn>
        </v-card-actions>
      </v-card>
    </div>


  </v-container>
</template>

<script>
export default {
  name: "Inscription",

  methods: {
    insc () {
      this.loading = true
      setTimeout(() => (this.loading = false), 1500)
    },
  },
}
</script>
