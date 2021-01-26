<template>
  <v-container>
    <v-data-table
        :headers="headers"
        :items="desserts"
        :items-per-page="10"
        item-key="name"
        class="elevation-1"
        hide-default-footer
        style="white-space: pre;"
    ></v-data-table>
  </v-container>

</template>

<script>
  export default {

    name: "Planning",
    data () {
      return {
        headers: [
          {
            text: 'Horaire',
            align: 'start',
            value: 'name',
            sortable: false
          },
          {
            text: 'Sujet de la conférence',
            value: 'category',
            sortable: false
          },
          {
            text: "Intervenant·e·s",
            value: 'intervenant',
            sortable: false
          }
        ],
        desserts: [
          {
            name: '9h - 9h45',
            category: 'Présentation du logiciel libre',
            intervenant: 'Jean-Christophe BECQUET (Apitux)'
          },
          {
            name: '9h45 - 10h30',
            category: 'Logiciel libre, entreprises et modèles économiques.\n' +
                'Retour d\'expérience avec les sociétés Algoo et Worteks',
            intervenant: 'Clément OUDOT (Worteks)\nDamien ACCORSI (Algoo)'
          },
          {
            name: '10h45 - 11h30',
            category: 'Comment contribuer au logiciel libre ?',
            intervenant: 'Mélanie NGUYEN'
          },
        ],
      }
    },
  }
</script>

<style scoped>

</style>