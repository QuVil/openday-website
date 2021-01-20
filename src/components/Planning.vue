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
            name: '8h30 - 9h15',
            category: 'Présentation du logiciel libre',
            intervenant: 'A déterminer'
          },
          {
            name: '9h15 - 10h',
            category: 'L\'intérêt du logiciel libre en entreprise',
            intervenant: 'Clément OUDOT & Damien ACCORSI'
          },
          {
            name: '10h15 - 11h',
            category: 'Comment contribuer ?',
            intervenant: 'Melanie NGUYEN'
          },
          {
            name: '11h - 11h45',
            category: 'Le futur du logiciel libre',
            intervenant: 'A déterminer'
          },
        ],
      }
    },
  }
</script>

<style scoped>

</style>