<template>
	<div class="dark">
		<Header />
		<main class="min-h-screen bg-slate-950">
			<slot />
		</main>
		<Footer />
	</div>
</template>

<script setup>
definePageMeta({
	layout: "default",
});
</script>

<style scoped></style>
