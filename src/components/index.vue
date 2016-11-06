<template>
  <quasar-layout>
    <div slot="header" class="toolbar bg-positive" >
      <quasar-toolbar-title :padding="1" class="text-center">
        Provactive Problem Solver
      </quasar-toolbar-title>
    </div>

    <quasar-tabs slot="navigation">
      <quasar-tab route="/juliet">
          J
      </quasar-tab>

      <quasar-tab route="/noVowels">
          No Vwls
      </quasar-tab>

      <quasar-tab route="/qNoU">
          qNoU
      </quasar-tab>

      <quasar-tab route="/quebec">
          Q
      </quasar-tab>

      <quasar-tab route="/threeLetters">
          3 Ltrs
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

      <quasar-tab route="/twoLetters">
          2 Ltrs
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

<style >
.instruction {
  text-align: center
}

.wordStyle {
  border-bottom: 1px solid;
  width: 90%;
  margin-bottom: .5rem;
}

h3 {
  align-content: center;
}
</style>
