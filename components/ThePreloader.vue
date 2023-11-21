import type { set } from 'nuxt/dist/app/compat/capi';
<template>
	<div class="preloader">
		<div class="preloader__percent">{{ progress ? progress : 0 }}%</div>
	</div>
</template>

<script setup>
	import gsap from 'gsap';
	import { general } from '@/store/index.js';

	const DELAY_BETWEEN_PHOTO_LOADED = 15;
	const number_of_images_loaded = ref(0);
	const total_images = ref(0);

	const setProgress = total => {
		number_of_images_loaded.value++;
		total_images.value = total;
	};

	onMounted(async () => {
		const images = document.querySelectorAll('img');

		for (const img of images) {
			await new Promise(resolve => {
				if (img.complete) {
					setProgress(images.length);
					resolve();
				} else {
					img.onload = () => {
						setProgress(images.length);
						resolve();
					};
				}
			});

			await new Promise(resolve => {
				setTimeout(resolve, DELAY_BETWEEN_PHOTO_LOADED);
			});
		}
	});

	const progress = computed(() => {
		return Math.min(
			Math.floor((number_of_images_loaded.value / total_images.value) * 100),
			100
		);
	});

	watch(
		() => progress.value,
		number => {
			if (number === 100) {
				general.isPreloaderVisible = false;
				gsap.fromTo(
					'.preloader',
					{
						clipPath: 'polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%)',
					},
					{
						clipPath: 'polygon(100% 0%, 100% 0%, 100% 100%, 100% 100%)',
						duration: 1.2,
						ease: 'power4.out',
						onComplete: () => {
							gsap.set('body', {
								overflow: 'auto',
							});
						},
					}
				);
			}
		}
	);
</script>

<style lang="scss" scoped>
	.preloader {
		position: fixed;
		inset: 0;
		z-index: 10;
		background: #000;
		color: #fff;

		font-size: 6vw;
		// letter-spacing: -0.1em;

		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
