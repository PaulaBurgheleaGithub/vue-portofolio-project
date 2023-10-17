<template>

  <div class="UserView">
    <ThumbGrid 
      :projects2="projects"
      @click="displayFeatured"
    />
  </div>
</template>

<script>
import ThumbGrid from "./ThumbGrid.vue";

export default {
  name: "UserView",

  components: {
    ThumbGrid
  },

  props: ["projects", "displayFeatured"],

  data() {
    return {
      featured: this.projects[0],
    }
  },
  methods: {
    setFeatured(id) {
      this.featured = displayFeatured;
    }
  }
};

</script>

<style>

.featured {
  margin: 30px 0;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 30px;

}
.featured > div {
  width: 50%;
}

featured_image {
  width: 100px;
	object-fit: cover;
	aspect-ratio: 1/1;
}

/* figcaption,
blockquote {
  top: 0;
  right: 0
} */
</style>
