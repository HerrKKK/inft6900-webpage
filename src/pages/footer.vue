<!-- 
  2022 Trimester 3 INFT6900 Final Project
  Team   : Four Square
  Author : Chao Zhang
  Date   : 03/11/2022
-->

<template>
  <v-footer
      color="rgb(11,11,11)"
      padless
      fixed
  >
    <v-row
        justify="center"
        no-gutters
    >
      <v-btn
          v-for="link in links"
          :key="link.text"
          color="white"
          text
          rounded
          class="my-2"
          @click="openLink(link.link)"
      >
        {{ link.text }}
      </v-btn>
    </v-row>
  </v-footer>
</template>

<script>
export default {
  name: "FooterPage",
  data: () => ({
    links: [
      {
        text: 'UoN Home Page',
        link: 'https://www.newcastle.edu.au/'
      },
      {
        text: 'Canvas',
        link: 'https://canvas.newcastle.edu.au/'
      },
      {
        text: 'MyUni',
        link: 'https://myuni.newcastle.edu.au/'
      },
      {
        text: 'Library',
        link: 'https://newcastle.summon.serialssolutions.com/'
      },
    ],
  }),
  methods: {
    openLink(link) {
      window.open(link, '_blank')
    }
  }
}
</script>

<style scoped>
.v-btn {
  text-transform: none;
}
</style>