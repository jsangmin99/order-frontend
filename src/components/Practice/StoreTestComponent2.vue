<template>
  <h1>store test component2</h1>
  <p>count: {{getCount}}</p>
  <v-btn color="red" @click="incrementCount">increment</v-btn>
  <br>
  <input type="text" v-model="message">
  <v-btn color="red" @click="updateMessage">update message</v-btn>
</template>

<script>
import {mapGetters} from 'vuex';

export default {
  data() {
    return {
      count: 0,
      message: ""
    }
  },
  computed: {
    ...mapGetters(['getCount']),
  },
  methods: {
    incrementCount() {
      // this.count++
      this.$store.dispatch('incrementCount')
    },
    updateMessage() {
      this.$store.dispatch('updateMessage', this.message)
    },

  }
}

</script>