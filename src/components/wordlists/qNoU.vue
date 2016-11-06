<template>
<div>
  <ul>
    <li v-for="word in wordList">
      {{word.word}} - <span @click="$refs.basicModal.open()">Definition</span>
    </li>
  </ul>

  <!-- this shows the definition of the word when clicked on -->
  <quasar-modal
    ref="basicModal"
    class="maximized"
    @open="getDefinition(this)"
  >
    <h3>{{word}} Definition</h3>
    {{definition}}
    <button class="primary" @click="$refs.basicModal.close()">Close</button>
  </quasar-modal>
</div>
</template>

<script>
export default {
  data () {
    return {
      wordList: '',
      modalOpen: false,
      definition: ''
    }
  },

  methods: {
    getDefinition (word) {
      var that = this

      this.$http.get('https://wordsapiv1.p.mashape.com/words/%7Bword%7D/definitions')
      .then(function (response) {
        that.definition = response.definitions[0].definition
      })
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
