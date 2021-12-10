<template>
  <section class="image_item_container">
    <img :src="item.image" :alt="item.desc" />
    <footer class="footer">Add to favorites</footer>
  </section>
</template>

<script>
export default {
  props: {
    item: { type: Object, default: () => {} },
    action: { type: String },
    icon: { type: String },
    title: { type: String },
    class: { type: String },
  },
};
</script>

<style></style>
