<template>
  <section class="disc-section">
    <div class="container">
      <div class="row row-cols-2 row-cols-md-4 row-cols-lg-5">
        <AppDiscCard v-for="(item, index) in this.discs" :key="index" :discObj="item" />
      </div>
    </div>
  </section>
</template>

<script>
import AppDiscCard from "./AppDiscCard.vue";
import axios from "axios";

export default {
  name: "AppDiscSection",
  components: {
    AppDiscCard
  },
  data() {
    return {
      discs: []
    }
  },
  created() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then((resp) => {
      this.discs = resp.data.response;
      console.log(this.discs);
    });
  },
};
</script>

<style lang="scss" scoped>
@import "../style/common.scss";

.disc-section {
  background-color: #1e2d3b;
  width: 100%;
  height: calc(100vh - 82px );
  padding-top: 3rem;
  .container {
    height: 400px;
  }
}
</style>