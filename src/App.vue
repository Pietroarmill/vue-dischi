<template>
  <div id="app">
    <AppHeader />
    <AppDiscSection />
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppDiscSection from "./components/AppDiscSection.vue";

export default {
  name: 'App',
  components: {
    AppHeader,
    AppDiscSection,
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
@import "./style/common.scss";

</style>
