<!-- 
  2022 Trimester 3 INFT6900 Final Project
  Team   : Four Square
  Author : Weiran Wang
  Date   : 31/10/2022
-->

<template>
      <v-menu
        ref="menu"
        v-model="menu"
        :close-on-content-click="false"
        :nudge-right="40"
        :return-value.sync="time"
        transition="scale-transition"
        offset-y
        max-width="290px"
        min-width="290px"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-text-field
              v-model="time"
              :label="label"
              prepend-icon="mdi-clock-time-four-outline"
              readonly
              v-bind="attrs"
              v-on="on"
          ></v-text-field>
        </template>
        <v-time-picker
            v-if="menu"
            v-model="time"
            format="24hr"
            full-width
            @click:minute="$refs.menu.save(time)"
        ></v-time-picker>
      </v-menu>
</template>

<script>
export default {
  name: "TimeMenu",
  props: {
    label: String,
    initTime: String,
  },
  data () {
    return {
      time: null,
      menu: false,
    }
  },
  created() {
    this.time = this.initTime
  },
  watch: {
    initTime: {
      handler(newTime) {
        this.time = newTime
      }
    }
  }
}
</script>

<style scoped>

</style>