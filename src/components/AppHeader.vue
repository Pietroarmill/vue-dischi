<template>
  <section class="header">
    <div class="header__img">
      <img src="../assets/img/logo-small.svg" alt="">
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHeader",
}
</script>

<style lang="scss" scoped>
@import "../style/common.scss";

.header {
  background-color: #2e3a46;
  padding: 1rem;
  height: 90px;
  &__img {
    width: 50px;
  }
}
</style>