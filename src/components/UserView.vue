<template>
  <div class="featured">
    <figure>
      <img :src="featured.image" 
        :alt="featured.title"
      />
      <figcaption><b>{{featured.title}}</b></figcaption>
      <blockquote>{{featured.details}}</blockquote>

    </figure>
  </div>
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

  props: ["projects"],

  data() {
    return {
      featured: this.projects[0]
    }
  }
};

</script>

<style>
figure,
blockquote {
  margin:0;
  width: 100%;
}
.featured {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
}
.featured img {
  width: 50%;
  height: auto;
  object-fit: cover;
	aspect-ratio: 1/1;
}
figcaption,
blockquote {
  top: 0;
  right: 0
}
</style>
