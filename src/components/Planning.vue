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
          },
          { text: 'Sujet de la conférence', value: 'category' },
          { text: "Intervenant", value: 'intervenant'}
        ],
        desserts: [
          {
            name: '9h - 9h 45',
            category: 'Présentation du logiciel libre',
            intervenant: 'A déterminer'
          },
          {
            name: '9h 45 - 10h 30',
            category: 'L\'intérêt du logiciel libre en entreprise',
            intervenant: 'A déterminer'
          },
          {
            name: '10h 45 - 10h 30',
            category: 'Comment contribuer ?',
            intervenant: 'A déterminer'
          },
          {
            name: '11h 30 - 12h 15',
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