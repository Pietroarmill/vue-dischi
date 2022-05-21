<template>
  <section class="d-flex mb-3">
    <div class="flex-grow-1 form-group me-2">
      <input 
        type="text"
        class="form-control"
        placeholder="Enter Disc"
        v-model="searchWord"
        @keyup="$emit('searchClicked', searchWord)"
      >
    </div>
    <button class="p-1" @click="$emit('searchClicked', searchWord)">
      CERCA
    </button>
    <button class="p-1">RESET</button>
  </section>
</template>

<script>
export default {
  name: "AppSearch",
  data() {
    return {
      searchWord: '',
    };
  },
};
</script>

<style lang="scss" scoped>
</style>