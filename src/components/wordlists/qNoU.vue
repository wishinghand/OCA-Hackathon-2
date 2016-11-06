<template>
<div>
  <ul>
    <li v-for="word in wordList">
      {{word.word}} - <span @click="openModal(word.word)" :id="word.word">Definition</span>
    </li>
  </ul>

  <!-- this shows the definition of the word when clicked on -->
  <quasar-modal
    ref="basicModal"
    class="maximized"
    @open="getDefinition()"
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
    openModal (word) {
      this.$refs.basicModal.open()
      this.getDefinition(word)
    },
    getDefinition (word) {
      var that = this

      this.$http.get('https://wordsapiv1.p.mashape.com/words/' + word + '/definitions')
      .then(function (response) {
        that.definition = response.definitions[0].definition
      })
      .catch(function (error) {
        console.log(error)
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
