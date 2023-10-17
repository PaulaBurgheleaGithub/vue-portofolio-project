<template>
	<div>
		<div class="featured">

			<div class="featured_image">
				<img :src="featured.image" :alt="featured.title">
			</div>

			<div>
				<h3>{{ featured.title }}</h3>
				<p>{{ featured.details }}</p>
			</div>
		</div>

		<div className="ThumbGrid">
			<img v-for="(p, i) in projects2"
				:key="i"
				:src="p.image"
				:alt="p.title"
				@click="$event => setFeatured(p)"
			/>
		</div>
	</div>

</template>

<script>
export default {
	name: 'ThumbGrid',

	props: ["projects2"],

	emits: ["displayFeatured"],

	methods:{
		setFeatured(project) {
			this.featured = project;
			this.emits("displayFeatured", project);
		}
	},
	data() {
		return {
			featured : this.projects2[0]
		}
	}
}
</script>

<style>
.featured {
	margin: 30px 0;
	display: grid;
	grid-template-columns: repeat(2, 1fr);
	gap: 30px;
}
/* .featured > div {
  width: 100%;
} */

.featured_image {
	width: 100%;
}
.featured_image img {
	width: 300px;
	height: auto;
	object-fit: cover;
	aspect-ratio: 1/1;
	border: 5px solid rgb(239, 236, 236);
}

.ThumbGrid {
	display: grid;
	grid-template-columns: repeat(4, 1fr);
	gap: 20px;
}

.ThumbGrid img {
	width: 100%;
	height: auto;
	object-fit: cover;
	aspect-ratio: 1/1;
	border: 5px solid rgb(239, 236, 236);
}

</style>
