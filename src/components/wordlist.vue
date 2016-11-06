<template>
  <quasar-layout>
    <p class="caption">{{selectedList}}</p>
    <div class="list" v-for="word in wordList">
      <div class="item">
        <div class="item-content">
          {{word.word}} - <span @click="openModal(word.word)">Definition</span>
        </div>
      </div>
      <hr>
    </div>

    <quasar-modal
      ref="basicModal"
      class="maximized"
    >
      <h3>{{returnedWord}} Definition</h3>
      <p>{{definition}}</p>
      <button class="primary" @click="$refs.basicModal.close()">Close</button>
    </quasar-modal>
  </quasar-layout>
</template>

<script>
export default {
  data () {
    return {
      wordList: '',
      definition: '',
      returnedWord: ''
    }
  },
  props: ['selectedList'],
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
      })
      .catch(function (error) {
        console.log(error)
      })
    }
  },
  updated () {
    console.log(this.selectedList)
    var that = this
    this.$http.get('../statics/' + this.selectedList + '.json')
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
