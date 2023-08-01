<template>
	<div className="ThumbGrid">
		<img v-for="p in projects2"
			:key="p.id"
			:src="p.image"
			:alt="p.title"
		/>
	</div>
</template>

<script>
export default {
	name: 'ThumbGrid',

	props: ["projects2"]
}
</script>

<style>
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
}
</style>
