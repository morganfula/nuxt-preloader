<template>
	<div id="viewport">
		<ThePreloader />
		<slot />
	</div>
</template>

<script setup></script>

<style lang="scss">
	*,
	*::after,
	*::before {
		box-sizing: border-box;
		padding: 0;
		margin: 0;

		border: 1px solid red;
	}

	body {
		background-color: rgb(58, 58, 58);
		overflow: hidden;
		-webkit-font-smoothing: antialiased;
		-mos-osx-font-smoothing: grayscale;
		color: white;
	}
</style>
