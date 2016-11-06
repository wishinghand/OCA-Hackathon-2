<template>
  <quasar-layout>
    <div slot="header" class="toolbar">
      <quasar-toolbar-title :padding="1">
        Provactive Problem Solver
      </quasar-toolbar-title>
    </div>

    <quasar-tabs slot="navigation">
      <quasar-tab route="/juliet">
          J
      </quasar-tab>

      <quasar-tab route="/noVowels">
          V
      </quasar-tab>

      <quasar-tab route="/qNoU">
          qNoU
      </quasar-tab>

      <quasar-tab route="/quebec">
          Q
      </quasar-tab>

      <quasar-tab route="/threeLetters">
          LLL
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
          LL
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
    <!--
      Replace following "div" with
      "<router-view class="layout-view">" component
      if using subRoutes
    -->
    <!-- <div class="layout-view"></div> -->

    <router-view class="layout-view"></router-view>
  </quasar-layout>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  computed: {
  },
  methods: {
  },
  mounted () {
  }
}
</script>

<style >

</style>
