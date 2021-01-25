<template>
  <v-container>
    <v-data-table
        :headers="headers"
        :items="desserts"
        :items-per-page="10"
        item-key="name"
        class="elevation-1"
        hide-default-footer
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
            intervenant: 'Jean-Christophe BECQUET'
          },
          {
            name: '9h45 - 10h30',
            category: 'L\'intérêt du logiciel libre en entreprise',
            intervenant: 'Clément OUDOT & Damien ACCORSI'
          },
          {
            name: '10h45 - 11h30',
            category: 'Comment contribuer au logiciel libre ?',
            intervenant: 'Mélanie NGUYEN'
          },
          {
            name: '11h30 - 12h15',
            category: 'A déterminer',
            intervenant: 'A déterminer'
          },
        ],
      }
    },
  }
</script>

<style scoped>

</style>