<template>
	<div class="dark">
		<Header />
		<main class="min-h-screen pt-[100px]">
			<slot />
		</main>
	</div>
</template>

<script setup>
definePageMeta({
	layout: "about",
});
</script>

<style scoped></style>
