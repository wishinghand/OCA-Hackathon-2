<template>
<div>
  <ul>
    <li v-for="word in wordList">
      {{word.word}} - <span @click="openModal(word.word)">Definition</span>
    </li>
  </ul>

  <!-- this shows the definition of the word when clicked on -->
  <quasar-modal
    ref="basicModal"
    class="maximized"
  >
    <h3>{{returnedWord}} Definition</h3>
    <p>{{definition}}</p>
    <button class="primary" @click="$refs.basicModal.close()">Close</button>
  </quasar-modal>
</div>
</template>

<script>
export default {
  data () {
    return {
      wordList: '',
      returnedWord: '',
      definition: ''
    }
  },

  methods: {
    openModal (word) {
      this.$refs.basicModal.open()
      this.getDefinition(word)
    },
    getDefinition (word) {
      var endOfWord = word.slice(-3)
      if (endOfWord === '(S)') {
        word = word.slice(0, -3)
      }
      var that = this
      var config = {
        headers: {
          'X-Mashape-Key': 'Kikv2nFc5omsh2drxrkb4WTVObfGp132j70jsnSdDT5BS8A4eV',
          'Accept': 'application/json',
          'Content-Type': 'text/plain',
          'Access-Control-Allow-Origin': '*',
          'Access-Control-Allow-Headers': 'Origin, X-Requested-With, Content-Type, Accept'
        }
      }

      this.$http.get('https://wordsapiv1.p.mashape.com/words/' + word + '/definitions', config)
      .then(function (response) {
        console.log(response)
        that.definition = response.data.definitions[0].definition
        that.returnedWord = response.data.word
        that.returnedWord = that.returnedWord.charAt(0).toUpperCase() + that.returnedWord.slice(1)
      })
      .catch(function (error) {
        console.log(error)
      })
    }
  },

  mounted () {
    var that = this

    this.$http.get('../../statics/twoYankees.json')
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
