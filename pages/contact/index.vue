<script setup>
const { name } = useRoute();

const toCapitalize = (str) => {
	return str[0].toUpperCase() + str.slice(1, str.length);
};

useHead({
	title: `${toCapitalize(name)} | FakeStore`,
	meta: [
		{ name: "description", content: "My amazing site." },
		{ name: "author", content: "FarruxDEV" },
	],
});
</script>

<template>
	<div class="dark">
		<main>
			<div class="wrapper p-6 border-dashed border-slate-500">
				<div
					class="p-2 flex items-center justify-between shadow bg-slate-600 text-white rounded-xl">
					<h2 class="px-4 py-2">CONTACTS</h2>
					<button class="px-4 py-2 bg-red-500 rounded-xl">GO BACK</button>
				</div>
			</div>
		</main>
	</div>
</template>

<style scoped></style>
