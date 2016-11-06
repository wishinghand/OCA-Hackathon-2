<template>
<div>
  <ul>
    <li v-for="word in wordList">
      {{word.word}}
    </li>
  </ul>
</div>
</template>

<script>
export default {
  data () {
    return {
      wordList: ''
    }
  },
  mounted () {
    var that = this

    this.$http.get('../../statics/twoAlphas.json')
    .then(function (response) {
      that.wordList = response.data
    })
    .catch(function (error) {
      console.log(error)
    })
  }
}
</script>

<style>

</style>
