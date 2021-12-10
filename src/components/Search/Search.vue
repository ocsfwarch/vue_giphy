<template>
  <div className="search_container">
    <search-form
      :search-term="searchTerm"
      @set-search-term="setSearchTerm"
    ></search-form>
    <image-display :image-list="imageList"></image-display>
  </div>
</template>

<script>
//import { ref, watch } from "vue";
import SearchForm from "./SearchForm.vue";
import ImageDisplay from "../ImageDisplay/ImageDisplay.vue";
const LIMIT = 12;
const API_URL =
  "https://api.giphy.com/v1/gifs/search?api_key=GZKGwdu6xlIM0iV58yFKJOFLqj0NLXFw&q=";

export default {
  components: {
    SearchForm,
    ImageDisplay,
  },
  props: {
    searchTerm: String,
    updateSearchTerm: { type: Function },
  },
  /*
  setup(props) {
    // Set the data
    let imageList = ref([]);

    // Add the watcher
    watch("searchTerm", () => {
      if (props.searchTerm && props.searchTerm.length > 0) {
        let searchTerm = props.searchTerm.replace(/\s+/g, "+");
        const response = fetch(`${API_URL}${searchTerm}&limit=${LIMIT}`)
          .then((response) => response.json())
          .then(({ data }) => {
            const imgDisplay = data.map((item) => {
              return {
                id: item.id,
                image: item.images.original.url,
                desc: item.title,
              };
            });
            imageList = [...imgDisplay];
          })
          .catch((error) => console.log(error.message));
      }
    });

    // Add the methods
    function setSearchTerm(newTerm) {
      $emit("update-search-term", newTerm);
    }

    return {
      setSearchTerm: setSearchTerm,
      imageList: imageList.value,
    };
  }, // End setup
*/

  methods: {
    setSearchTerm(newTerm) {
      this.$emit("update-search-term", newTerm);
    },
    runSearch() {
      if (this.searchTerm && this.searchTerm.length > 0) {
        let searchTerm = this.searchTerm.replace(/\s+/g, "+");
        console.log(`${API_URL}${searchTerm}&limit=${LIMIT}`);
        const response = fetch(`${API_URL}${searchTerm}&limit=${LIMIT}`)
          .then((response) => response.json())
          .then(({ data }) => {
            const imgDisplay = data.map((item) => {
              return {
                id: item.id,
                image: item.images.original.url,
                desc: item.title,
              };
            });
            //console.log(imgDisplay);
            this.imageList = [...imgDisplay];
          })
          .catch((error) => console.log(error.message));
      }
    },
  }, // End methods
  watch: {
    searchTerm: function () {
      this.runSearch();
    },
  },
  data() {
    return {
      imageList: [],
    };
  },
};
</script>
