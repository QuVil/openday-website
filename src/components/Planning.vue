<template>
  <v-container>
    <div>
    <v-data-table
        :headers="headers"
        :items="desserts"
        :items-per-page="10"
        item-key="name"
        class="elevation-1"
        hide-default-footer
        style="white-space: pre;"
        width="100%"
    >
      <template #item.slide="{ value }">
        <a :href="`${publicPath}${value.file}`" download>
          {{ value.name }}
        </a>
      </template>
      <template #item.video="{ value }">
        <a :href="`${value}`">
          PeerTube
        </a>
      </template>
    </v-data-table>

    </div>
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
          },
          {
            text: "Présentation",
            value: 'slide',
            sortable: false
          },
          {
            text: "Vidéo",
            value: 'video',
            sortable: false
          }
        ],
        desserts: [
          {
            name: '9h - 9h45',
            category: 'Présentation du logiciel libre',
            intervenant: 'Jean-Christophe BECQUET (Apitux)',
            slide: {
              file: "1.pdf",
              name: "Présentation 1"
            },
            video: "https://tube.nocturlab.fr/videos/watch/684aa6b8-c0ca-4bcd-8320-89d542e219d4"
          },
          {
            name: '9h45 - 10h30',
            category: 'Logiciel libre, entreprises et modèles économiques.\n' +
                'Retour d\'expérience avec les sociétés Algoo et Worteks',
            intervenant: 'Clément OUDOT (Worteks)\nDamien ACCORSI (Algoo)',
            slide: {
              file: "2.pdf",
              name: "Présentation 2"
            },
            video: "https://tube.nocturlab.fr/videos/watch/684aa6b8-c0ca-4bcd-8320-89d542e219d4"
          },
          {
            name: '10h45 - 11h30',
            category: 'Comment contribuer au logiciel libre ?',
            intervenant: 'Mélanie NGUYEN',
            slide: {
              file: "3.pdf",
              name: "Présentation 3"
            },
            video: "https://tube.nocturlab.fr/videos/watch/6c99f648-b3b2-489c-bcd4-373b2df26e82"
          },
          {
            name: '11h30 - 12h15',
            category: 'Favoriser l\'auto-hébergement des données personnelles avec un Raspberry \nderrière sa box au lieu de consommer du data-center américain.',
            intervenant: 'Marc HEPIEGNE (Oisux)\nSamuel VERMEULEN (Oisux)\nJean-Louis LECORNU (Oisux)',
            slide: {
              file: "4.zip",
              name: "Présentation 4"
            },
            video: "https://tube.nocturlab.fr/videos/watch/270229ac-9570-4bc6-ad54-71e032103f73"
          },
        ],
        publicPath: process.env.BASE_URL
      }
    },
  }
</script>

<style scoped>

</style>