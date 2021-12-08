<template>
  <section className="search_form_container">
    <form id="gif_search_form" name="gif_search_form" v-on:submit="search">
      <label for="search_gif">
        <input
          type="text"
          id="search_gif"
          name="search_gif"
          placeholder="Enter a search term"
          :value="searchTerm"
          required
        />
      </label>
      <button className="btn_green" type="submit">Search</button>
    </form>
  </section>
</template>

<script>
export default {
  props: {
    searchTerm: { type: String, required: true },
    setSearchTerm: { type: Function },
  },
  methods: {
    search(event) {
      event.preventDefault();
      this.$emit("set-search-term", event.target.search_gif.value);
    },
  },
};
</script>
