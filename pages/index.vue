<template>
	<div class="gallery">
		<div class="gallery__wrap" v-for="_ in 10">
			<div class="gallery__item" v-for="img in images">
				<img class="gallery__img" :src="img" alt="" />
			</div>
		</div>
	</div>
</template>

<script setup>
	const images = [
		'1.jpg',
		'2.jpg',
		'3.jpg',
		'4.jpg',
		'5.jpg',
		'6.jpg',
		'7.jpg',
		'8.jpg',
		'9.jpg',
		'10.jpg',
		'11.jpg',
		'12.jpg',
	];
</script>

<style lang="scss" scoped>
	.gallery__wrap {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
	}
	.gallery__item {
		height: 20vw;
	}
	.gallery__img {
		vertical-align: top;
		width: 100%;
		height: 100%;
		object-fit: cover;
		object-position: center;
	}
</style>
