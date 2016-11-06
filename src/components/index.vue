<template>
  <quasar-layout>
    <div slot="header" class="toolbar">
      <quasar-toolbar-title :padding="1">
        Provactive Problem Solver
      </quasar-toolbar-title>
    </div>

    <quasar-tabs slot="navigation">
      <quasar-tab @click="selectedList = juliet">
          J
      </quasar-tab>

      <quasar-tab @click="selectedList = noVowels">
          No Vwls
      </quasar-tab>

      <quasar-tab @click="selectedList = qNoU">
          qNoU
      </quasar-tab>

      <quasar-tab @click="selectedList = quebec">
          Q
      </quasar-tab>

      <quasar-tab @click="selectedList = threeLetters">
          3 Ltrs
      </quasar-tab>

      <quasar-tab @click="selectedList = twoAlphas">
          AA
      </quasar-tab>

      <quasar-tab @click="selectedList = twoEchos">
          EE
      </quasar-tab>

      <quasar-tab @click="selectedList = twoIndias">
          II
      </quasar-tab>

      <quasar-tab @click="selectedList = twoLetters">
          2 Ltrs
      </quasar-tab>

      <quasar-tab @click="selectedList = twoOctobers">
          OO
      </quasar-tab>

      <quasar-tab @click="selectedList = twoUnicorns">
          UU
      </quasar-tab>

      <quasar-tab @click="selectedList = twoYankees">
          YY
      </quasar-tab>

      <quasar-tab @click="selectedList = xray">
          X
      </quasar-tab>

      <quasar-tab @click="selectedList = zebra">
          Z
      </quasar-tab>
    </quasar-tabs>
    <!-- <div class="layout-view"></div> -->
    <word-list :selectedList="selectedList"></word-list>
  </quasar-layout>
</template>

<script>
import wordList from './wordlist'

export default {
  components: {
    wordList
  },
  data () {
    return {
      selectedList: ''
    }
  }
}
</script>

<style >

</style>
