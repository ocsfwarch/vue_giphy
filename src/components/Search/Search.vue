<script setup>
import SearchForm from "./SearchForm.vue";
</script>
<script>
export default {
  props: {
    searchTerm: String,
    updateSearchTerm: { type: Function },
  },
  methods: {
    setSearchTerm(newTerm) {
      //console.log(`Got a new term = ${newTerm}`);
      //event.preventDefault();
      //this.searchTerm = newTerm;
      this.$emit("update-search-term", newTerm);
    },
  },
};
</script>

<template>
  <div className="search_container">
    <SearchForm :search-term="searchTerm" @set-search-term="setSearchTerm" />
  </div>
</template>
