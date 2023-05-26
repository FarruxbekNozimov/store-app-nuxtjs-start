<script setup>
import Title from "@/components/Title.vue";
const { data } = useFetch("https://fakestoreapi.com/products");

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
				<Title />
				<div
					class="mt-10 grid lg:grid-cols-4 md:grid-cols-3 sm:grid-cols-2 gap-5">
					<Card v-for="el in data" :product="el" />
				</div>
			</div>
		</main>
	</div>
</template>

<style scoped></style>
