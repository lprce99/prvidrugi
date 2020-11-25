
<template lang="html">
  <div class="wrapper">
    <button class="change__style" @click="changeStyle()">
      Change style
    </button>
    <tabs
      :mode="mode"
    >
      <tab title="Simple Apartment Manager">
        <Tablica :apartments="apartments"></Tablica>
      </tab>
      <tab title="Code Challenge">
        <Challenge></Challenge>
      </tab>
    </tabs>
  </div>
</template>

<script>
import Challenge from '../components/CodingChalange.vue'
import Tab from './Tab.vue'
import Tabs from './Tabs.vue'

export default {
  components: {
    Tab,
    Tabs,
    Challenge
  },
  data () {
    return {
      mode: 'dark',
      apartments: 'naziv'
    }
  },
  created () {
    this.getapartments()
  },
  methods: {
    changeStyle () {
      if (this.mode === 'dark') {
        this.mode = 'light'
      } else {
        this.mode = 'dark'
      }
    },
    getapartments () {
      this.$axios.get('objects').then((response) => {
        this.apartments = response.data
      })
    }
  }
}
</script>

<style lang="css">
  * {
    margin: 0;
    padding: 0;
    font-family: 'Karla', sans-serif;
  }
  .wrapper {
    width: 100%;
    min-height: 100vh;
    background-color: #f8f8f8;
    margin: 0;
    padding: 20px;
  }

  .change__style {
    background-color: #eee;
    font-size: 1em;
    margin-bottom: 10px;
    padding: 5px;
  }
</style>
