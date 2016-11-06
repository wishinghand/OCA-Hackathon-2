<template>
<div>
J
  <ul>
    <li v-for="(word, index) in wordList">
      {{word[index].word}}
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

    this.$http.get('../../statics/juliet.json')
    .then(function (response) {
      console.log(response.data)
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
