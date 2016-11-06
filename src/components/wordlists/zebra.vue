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
    this.$http.get('../../statics/zebra.json')
    .then(function (response) {
      console.log(response)
      this.wordList = response.body
    })
    .catch(function (error) {
      console.log(error)
    })
  }
}
</script>

<style>

</style>
