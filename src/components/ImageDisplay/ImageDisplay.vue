<template>
  <div class="image_display_container">
    <section class="image_list">
      <ul>
        <li v-for="item in imageList">
          <image-list-item :item="item"></image-list-item>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
import ImageListItem from "./ImageListItem.vue";
export default {
  components: {
    ImageListItem,
  },
  props: {
    imageList: { type: Array },
  },
};
</script>

<style>
/* This file contains the styling information
   for the ImageDisplay component.
*/
img {
  max-height: 100%;
  max-width: 100%;
}

.image_display_container {
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
  background-color: white;
  padding-top: 5px;
  overflow-y: auto;
  -webkit-overflow-scrolling: touch;
}

.image_display_container .hide_list {
  opacity: 0;
}

.image_display_container .image_list {
  width: 100%;
  overflow-y: scroll;
  background-color: transparent;
}

.image_display_container .show_none {
  display: flex;
  justify-self: center;
  align-items: center;
  height: 100%;
  width: 100%;
  background-color: gray;
}

.image_display_container .image_list ul {
  list-style-type: none;
  background-color: transparent;
}

.image_display_container .image_list li {
  background-color: transparent;
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  width: 90%;
  margin-bottom: 1em;
  border: 0.0625em solid #a3a3a3;
  border-radius: 0.5em;
  padding: 1px;
  box-shadow: 5px 5px 5px 3px grey;
}

.image_display_container .image_item_container {
  background-color: transparent;
}

.image_display_container .image_item_container img {
  height: 20em;
  width: 20em;
  border-radius: 0.5em;
  transition: all 500ms;
}

.image_display_container .image_item_container .footer {
  flex: 0 0 auto;
  height: 2em;
  padding-left: 1em;
  cursor: pointer;
  background-color: transparent;
}

.image_display_container .image_item_container .footer label {
  cursor: pointer;
}

.image_display_container .image_item_container .footer .add {
  cursor: pointer;
  color: gold;
  padding-right: 0.5em;
}

.image_display_container .image_item_container .footer .remove {
  cursor: pointer;
  color: red;
  padding-right: 0.5em;
}

@media (min-width: 600px) {
  .image_display_container .image_list ul {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
    grid-auto-rows: minmax(100px, auto);
  }
}

@media (min-width: 800px) {
  .image_display_container .image_list ul {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    grid-auto-rows: minmax(100px, auto);
  }
}
</style>
