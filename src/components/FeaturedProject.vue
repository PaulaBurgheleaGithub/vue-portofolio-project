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
</template>

<script>

export default {
	name: 'FeaturedProject',

	props: ['featured']
}

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
