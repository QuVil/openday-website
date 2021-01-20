<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        Inscription obligatoire pour participer à l'événement.<br>
        Fermeture des inscrption le dimanche 31 janvier.<br>
        Les adresses mails seront seulement utilisées pour vous envoyer le lien de la plateforme de visioconférence quelques jours avant l'événement.
        Toutes les données enregistrées seront supprimées après l'événement.

      </v-col>
    </v-row>
    <v-row class="text-center">
      <v-col cols="12"><v-btn
        class="mr-4"
        large
        color="success"
        href='https://framaforms.org/inscription-openday-1611136545-0'
    >
      S'inscrire à l'OpenDay
    </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { validationMixin } from 'vuelidate'
import { required, email } from 'vuelidate/lib/validators'
import{ init } from 'emailjs-com';
init("user_WkqQuxnLlhvIGVwQZeVJD");
export default {
  name: "Inscription",
  mixins: [validationMixin],
  validations: {
    email: { required, email },
    checkbox: {
      checked (val) {
        return val
      },
    },
    phone: {required}
  },
}
</script>

<codepen-resources lang="json">
{
"js": [
"https://cdn.jsdelivr.net/npm/vuelidate/dist/vuelidate.min.js",
"https://cdn.jsdelivr.net/npm/vuelidate/dist/validators.min.js"
]
}
</codepen-resources>

<codepen-additional>
const { required, maxLength, email } = validators
const validationMixin = vuelidate.validationMixin

Vue.use(vuelidate.default)
</codepen-additional>

<style scoped>

</style>