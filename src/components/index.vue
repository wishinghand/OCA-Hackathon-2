<template>
  <quasar-layout>
    <div slot="header" class="toolbar">
      <quasar-toolbar-title :padding="1">
        Provactive Problem Solver
      </quasar-toolbar-title>
    </div>

    <quasar-tabs slot="navigation">
      <quasar-tab route="/wordlist/juliet">
          J
      </quasar-tab>

      <quasar-tab route="/wordlist/noVowels">
          No Vowels
      </quasar-tab>

      <quasar-tab route="/wordlist/quebec">
          Q
      </quasar-tab>

      <quasar-tab route="/wordlist/qNoU">
          Q no U
      </quasar-tab>

      <quasar-tab route="/wordlist/xray">
          X
      </quasar-tab>

      <quasar-tab route="/wordlist/zebra">
          Z
      </quasar-tab>

      <quasar-tab route="/wordlist/twoLetters">
          2 Letters
      </quasar-tab>

      <quasar-tab route="/wordlist/threeLetters">
          3 Letters
      </quasar-tab>

      <quasar-tab route="/wordlist/twoAlphas">
          AA
      </quasar-tab>

      <quasar-tab route="/wordlist/twoEchos">
          EE
      </quasar-tab>

      <quasar-tab route="/wordlist/twoIndias">
          II
      </quasar-tab>

      <quasar-tab route="/wordlist/twoOctobers">
          OO
      </quasar-tab>

      <quasar-tab route="/wordlist/twoUnicorns">
          UU
      </quasar-tab>

      <quasar-tab route="/wordlist/twoYankees">
          YY
      </quasar-tab>
    </quasar-tabs>

    <router-view class="layout-view" ></router-view>
  </quasar-layout>
</template>

<script>
export default {
  data () {
    return {
      selectedList: ''
    }
  }
}
</script>

<style >

</style>
