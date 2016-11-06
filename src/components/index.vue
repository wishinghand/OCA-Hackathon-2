<template>
  <quasar-layout>
    <div slot="header" class="toolbar bg-amber-2" >
      <quasar-toolbar-title :padding="1" class="text-center text-brown-10">
        Provocative Problem Solver
      </quasar-toolbar-title>
    </div>

    <quasar-tabs slot="navigation" class="bg-brown-10">
      <quasar-tab route="/juliet">
          J
      </quasar-tab>

      <quasar-tab route="/noVowels">
          No Vowels
      </quasar-tab>

      <quasar-tab route="/qNoU">
          Q no U
      </quasar-tab>

      <quasar-tab route="/quebec">
          Q
      </quasar-tab>

      <quasar-tab route="/twoLetters">
          2 Letters
      </quasar-tab>

      <quasar-tab route="/threeLetters">
          3 Letters
      </quasar-tab>

      <quasar-tab route="/twoAlphas">
          AA
      </quasar-tab>

      <quasar-tab route="/twoEchos">
          EE
      </quasar-tab>

      <quasar-tab route="/twoIndias">
          II
      </quasar-tab>

      <quasar-tab route="/twoOctobers">
          OO
      </quasar-tab>

      <quasar-tab route="/twoUnicorns">
          UU
      </quasar-tab>

      <quasar-tab route="/twoYankees">
          YY
      </quasar-tab>

      <quasar-tab route="/xray">
          X
      </quasar-tab>

      <quasar-tab route="/zebra">
          Z
      </quasar-tab>
    </quasar-tabs>
    <!-- <div class="layout-view"></div> -->
    <router-view class="layout-view" ></router-view>
  </quasar-layout>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>

<style>

  li {
    list-style: none;
  }

  .instruction {
    text-align: center;
    font-style: italic;
  }

  .wordStyle {
    width: 66%;
    margin-bottom: .5rem;
    padding: .25rem;
  }

  .defText {
    padding: 1.5rem;
  }

  #defPage {
    background-color: #F9E3AB;
    color: #632612;
  }

</style>
