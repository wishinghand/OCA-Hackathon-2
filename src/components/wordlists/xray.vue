<template>
<div><br>
<p class="instruction">click on a word to see its meaning!</p>
  <ul>
    <li v-for="word in wordList" class="wordStyle">
      <span @click="openModal(word.word)">{{word.word}}</span>
    </li>
  </ul>

  <!-- this shows the definition of the word when clicked on -->
  <quasar-modal
    id="defPage"
    ref="basicModal"
    class="maximize"
    :content-css="{backgroundColor: '#F9E3AB'}"
  >

    <h4 class="text-center">Definition of <b>{{returnedWord}}</b></h4>
    <p class="defText">{{definition}}</p>
    <button class="round closeBtn" @click="$refs.basicModal.close()">Close</button>
    
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
      // clears modal when opening a new page
      this.returnedWord = ''
      this.definition = ''
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

    this.$http.get('../../statics/xray.json')
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
  .defPage {
    background-color: #F9E3AB;
  }

  .closeBtn {
    margin-left: 8rem;
    background-color: #632612;
    color: lightblue;
  }
</style>
