<template lang="html">
  <div>
    <h1>Challenge</h1>
    <textarea v-model="myWord" @input="countChars"></textarea>
    <div v-if="maxChar">Max Char:{{maxChar}} times: {{counts[maxChar]}}</div>
    <div>{{myWord}}</div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      myWord: '',
      counts: {},
      maxChar: null
    }
  },
  methods: {
    countChars () {
      this.counts = {}
      let index, len, ch, count
      for (index = 0, len = this.myWord.length; index < len; ++index) {
        ch = this.myWord.charAt(index)
        count = this.counts[ch]
        this.counts[ch] = count ? count + 1 : 1
      }
      let maxVal = 0
      this.maxChar = null
      Object.keys(this.counts).forEach((item) => {
        if (this.counts[item] > maxVal) {
          this.maxChar = item
          maxVal = this.counts[item]
        }
      })
    }
  }
}
</script>
