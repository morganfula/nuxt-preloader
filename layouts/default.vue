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
		font-family: 'Dirtyline';

		src: url('Dirtyline.woff') format('woff'),
			url('Dirtyline.woff2') format('woff2'),
			url('Dirtyline.ttf') format('truetype'); /* Safari, Android, iOS */
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
		background-color: rgb(58, 58, 58);
		overflow: hidden;
		-webkit-font-smoothing: antialiased;
		-mos-osx-font-smoothing: grayscale;
		color: white;

		font-family: 'Dirtyline';
	}
</style>
