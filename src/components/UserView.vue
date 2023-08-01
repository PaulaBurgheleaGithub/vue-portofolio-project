<template>
  <div class="UserView">
    <ThumbGrid :projects2="projects"/>
  </div>
</template>

<script>
import ThumbGrid from "./ThumbGrid.vue"

export default {
  name: "UserView",

  components: {
    ThumbGrid
  },

  props: ["projects"]
};

</script>

<style></style>
