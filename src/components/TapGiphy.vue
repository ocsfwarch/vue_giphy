<script setup>
import Header from "./Header.vue";
import Status from "./Status.vue";
import Search from "./Search/Search.vue";
import { defineComponent } from "@vue/runtime-core";
</script>

<script>
export default defineComponent({
  name: "TapGiphy",
  data() {
    return {
      searchTerm: "",
    };
  },
  methods: {
    updateSearchTerm(newTerm) {
      this.searchTerm = newTerm;
    },
  },
});
</script>

<template>
  <div class="app_container">
    <Header />
    <Status />
    <Search :search-term="searchTerm" @update-search-term="updateSearchTerm" />
  </div>
</template>

<style>
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen",
    "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue",
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

/* 
  Start - TapGiphy Styles
*/

.app_container {
  display: flex;
  flex-flow: column nowrap;
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  background-color: lightblue;
}

/* HEADER and NAVIGATION */
.app_header {
  flex: 0 0 auto;
  display: flex;
  flex-flow: column nowrap;
  width: 100%;
  background-color: white;
  border-radius: 0.25rem;
}

.app_header_banner {
  flex: 0 0 auto;
  height: 1.85em;
  width: 100%;
  font-size: 1.85em;
  font-weight: bold;
  color: #00006f;
  border-bottom: 1px skyblue solid;
  text-align: center;
}

.app_header_menu {
  flex: 0 0 auto;
  display: flex;
  height: 2em;
  flex-flow: row nowrap;
  justify-content: flex-start;
  align-items: center;
  width: 100%;
  background-color: white;
  border-radius: 0.25em;
  border-bottom: 1px skyblue solid;
}

.navContent {
  font-size: 1.25em;
  width: 100%;
  font-weight: bold;
}

.navContent a {
  text-decoration: none;
}

.navContent a:hover {
  color: green;
}

.navLinks {
  text-align: center;
}

.app_header_menu li {
  display: inline;
  padding-right: 1em;
}

.status {
  padding-left: 2em;
}

/* Main */
.main_container {
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
  background-color: white;
}

.main_container .dialog {
  flex: 0 1 auto;
  display: flex;
  flex-flow: column nowrap;
  width: 80%;
  height: 70%;
  word-wrap: break-word;
  background-color: white;
  border: 1px solid black;
  border-radius: 0.5em;
  box-shadow: 7px 10px gray;
  padding: 1px;
}

.main_container .dialog .header {
  flex: 0 0 auto;
  font-size: 1.5em;
  font-weight: 700;
  text-align: center;
  background-color: lightgray;
  border-top-right-radius: 0.25em;
  border-top-left-radius: 0.25em;
}

.main_container .dialog .content {
  flex: 1 1 auto;
  margin: 2em;
  background-color: transparent;
  text-align: left;
  padding: 4px;
  overflow-y: auto;
  -webkit-overflow-scrolling: touch;
}

.main_container .dialog .content .introduction {
  font-size: 1.25em;
  font-weight: 500;
}

.main_container .dialog .content .introduction a {
  text-decoration: none;
}

.main_container .dialog .footer {
  flex: 0 0 auto;
  display: flex;
  height: 2em;
  flex-flow: row nowrap;
  justify-content: flex-start;
  align-items: center;
  font-size: 1.25em;
  font-weight: 500;
  padding-left: 1em;
  background-color: lightgray;
  border-bottom-right-radius: 0.25em;
  border-bottom-left-radius: 0.25em;
}

.search_container {
  display: flex;
  flex-flow: column nowrap;
  background-color: gray;
  height: 100vh;
  width: 100vw;
  overflow: hidden;
}

.search_form_container {
  flex: 0 0 auto;
  display: flex;
  flex-flow: row nowrap;
  justify-content: center;
  align-items: center;
  height: 4rem;
  width: 100%;
  background-color: transparent;
}

.search_form_container label::after {
  content: " ";
}

/* Button Styling */
.search_form_container .btn_green {
  flex: 0 0 auto;
  width: 6rem;
  border: 0;
  line-height: 1.5;
  padding: 0 20px;
  font-size: 1rem;
  text-align: center;
  color: #fff;
  text-shadow: 1px 1px 1px #000;
  border-radius: 10px;
  background-color: rgb(0, 220, 0);
  background-image: linear-gradient(
    to top left,
    rgba(0, 0, 0, 0.2),
    rgba(0, 0, 0, 0.2) 30%,
    rgba(0, 0, 0, 0)
  );
  box-shadow: inset 2px 2px 3px rgba(255, 255, 255, 0.6),
    inset -2px -2px 3px rgba(0, 0, 0, 0.6);
  cursor: pointer;
}

.search_form_container .btn_green:hover {
  background-color: rgb(0, 255, 0);
}

.search_form_container .btn_green:active {
  box-shadow: inset -2px -2px 3px rgba(255, 255, 255, 0.6),
    inset 2px 2px 3px rgba(0, 0, 0, 0.6);
}

/* 
  End   - TapGiphy Styles
*/
</style>
