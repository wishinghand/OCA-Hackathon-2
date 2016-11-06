<template>
<div>
  <ul>
    <li v-for="word in wordList">
      {{word.word}} - <a href="#" @click="modalOpen = !modalOpen">Definition</a>
    </li>
  </ul>

  <quasar-modal ref="basicModal" class="minimized" v-show="modalOpen">
    <h2>Basic Modal</h2>
    <button class="primary" @click="$refs.basicModal.close()">Close</button>
  </quasar-modal>
</div>
</template>

<script>
export default {
  data () {
    return {
      wordList: '',
      modalOpen: false
    }
  },
  mounted () {
    var that = this

    this.$http.get('../../statics/qNoU.json')
    .then(function (response) {
      // console.log(response.data)
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
