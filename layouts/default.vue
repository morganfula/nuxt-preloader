<template>
	<div id="viewport">
		<ThePreloader />
		<slot />
	</div>
</template>

<script setup></script>

<style lang="scss">
	/* Webfont: Dirtyline36Daysoftype2022-Reg */
	@font-face {
		font-family: 'Chillax-Medium';

		src: url('/Chillax-Medium.woff') format('woff'),
			url('/Chillax-Medium.woff2') format('woff2'),
			url('/Chillax-Medium.ttf') format('truetype'); /* Safari, Android, iOS */
		font-style: normal;
		font-weight: normal;
		text-rendering: optimizeLegibility;
	}

	*,
	*::after,
	*::before {
		box-sizing: border-box;
		padding: 0;
		margin: 0;

		// border: 1px solid red;
	}

	/* Hide scrollbar for Chrome, Safari and Opera */
	body::-webkit-scrollbar {
		display: none;
	}

	/* Hide scrollbar for IE, Edge and Firefox */
	body {
		-ms-overflow-style: none; /* IE and Edge */
		scrollbar-width: none; /* Firefox */
	}

	body {
		background-color: #f6f3d6;
		overflow: hidden;
		-webkit-font-smoothing: antialiased;
		-mos-osx-font-smoothing: grayscale;
		color: white;

		font-family: 'Chillax-Medium';
	}
</style>
