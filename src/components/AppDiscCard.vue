<template>
  <div class="bg-disc-card">
    <div class="disc__card">
      <div class="img">
        <img :src="discObj.poster" alt="">
      </div>
      <div class="disc__card__name">
        <h2>{{ discObj.title }}</h2>
      </div>
      <div class="disc__card__author">
        <p>{{ discObj.author }}</p>
        <small>{{ discObj.year }}</small>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppDiscCard",
  props: {
    discObj: Object,
  },
}
</script>

<style lang="scss" scoped>
@import "../style/common.scss";

.bg-disc-card {
  margin-bottom: 1rem;
}

.disc__card {
  text-align: center;
  background-color: #2e3a46;
  padding: 10%;
  min-height: 400px;
  &__name {
    color: rgb(255, 255, 255);
    margin: 1rem 0;
    text-transform: uppercase;
    h2 {
      font-size: 1.5rem;
    }
  }
  &__author {
    color: #8c8d8f;
    p {
      font-size: 1.2rem;
    }
  }
}
</style>