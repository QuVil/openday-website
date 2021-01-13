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
            name: '8h 30 - 9h 15',
            category: 'Présentation du logiciel libre',
            intervenant: 'A déterminer'
          },
          {
            name: '9h 15 - 10h',
            category: 'L\'intérêt du logiciel libre en entreprise',
            intervenant: 'A déterminer'
          },
          {
            name: '10h 15 - 11h',
            category: 'Comment contribuer ?',
            intervenant: 'A déterminer'
          },
          {
            name: '11h - 11h 45',
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