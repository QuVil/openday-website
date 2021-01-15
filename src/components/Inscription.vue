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
    <form @submit.prevent="submit">
      <v-row class="text-center">
        <v-col cols="12"
        md="4"
        offset-md="4">
          <v-text-field
              v-model="email"
              :error-messages="emailErrors"
              label="E-mail"
              :required="true"
              @input="$v.email.$touch()"
              @blur="$v.email.$touch()"
              :name="email"
          ></v-text-field>

          <v-checkbox
              v-model="checkbox"
              label="Voulez vous recevoir un sms de rappel la veille de l'événement ?"
              @change="$v.checkbox.$touch()"
              @blur="$v.checkbox.$touch()"
          ></v-checkbox>
          <v-text-field
              v-model="phone"
              :disabled="!checkbox"
              :error-messages="phoneErrors"
              label="Numéro de téléphone"
              :required="checkbox"
              @input="$v.phone.$touch()"
              @blur="$v.phone.$touch()"
          ></v-text-field>

          <v-btn
              class="mr-4"
              @click="submit"
          >
            S'inscrire
          </v-btn>
        </v-col>
      </v-row>
    </form>
  </v-container>
</template>

<script>
import { validationMixin } from 'vuelidate'
import { required, email } from 'vuelidate/lib/validators'
import emailjs from 'emailjs-com';
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
  data: () => ({
    name: '',
    email: '',
    message: '',
    select: null,
    checkbox: false,
    phone: ''
  }),
  computed: {
    emailErrors () {
      const errors = []
      if (!this.$v.email.$dirty) return errors
      !this.$v.email.email && errors.push('E-mail non valide')
      !this.$v.email.required && errors.push('E-mail requis')
      return errors
    },
    phoneErrors() {
      const errors = []
      if (!this.$v.phone.$dirty) return errors
      !this.$v.phone.required && errors.push('Numéro de téléphone est requis pour recevoir un rappel par SMS')
      return errors
    }
  },
  methods: {
    submit () {
      this.$v.$touch()
      const err = this.emailErrors;
      const err2 = this.phoneErrors;
      if (err.length == 0 && (!this.checkbox || err2.length == 0)) {
        this.sendEmail()
        this.$router.push('/validate')
      }
    },
    sendEmail() {
      try {
        emailjs.send('service_mp0j73f', 'template_192lvme', {
              email: this.email,
              checked: this.checkbox,
              phone: this.phone
            },
            'user_WkqQuxnLlhvIGVwQZeVJD', )
        console.log("coucou")

      } catch(error) {
        console.log({error})
      }
      // Reset form field
      this.phone = ''
      this.email = ''
      this.message = ''
    },
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