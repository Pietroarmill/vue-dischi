<template>
  <section class="disc-section">
    <div class="container clearfix">
      <AppSearch @searchClicked="dataSearch($event)" />
      <div v-if="loading">loading</div>
      <div v-else class="row row-cols-2 row-cols-md-4 row-cols-lg-5">
        <AppDiscCard v-for="(item, index) in discsFilter" :key="index" :discObj="item" />
      </div>
    </div>
  </section>
</template>

<script>
import AppDiscCard from "./AppDiscCard.vue";
import AppSearch from "./AppSearch.vue"
import axios from "axios";

export default {
  name: "AppDiscSection",
  components: {
    AppDiscCard,
    AppSearch
  },
  computed: {
    discsFilter() {
      const filterArray = this.discs.filter((item) => {
        return item.title.toLowerCase().includes(this.wordSearch);
      });
      return filterArray;
    }
  },
  data() {
    return {
      discs: [],
      loading: true,
      wordSearch: '',
    };
  },
  created() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then((resp) => {
      this.discs = resp.data.response;
      console.log(this.discs);
      
      this.loading = false;
    });
  },
  methods: {
    dataSearch(word) {
      this.wordSearch = word.toLowerCase();
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../style/common.scss";

.disc-section {
  background-color: #1e2d3b;
  width: 100%;
  // height: calc(100vh - 82px );
  padding-top: 3rem;
  .container {
    min-height: calc(100vh - 138px);
  }
}
</style>