<script setup>
const { data, pending, error, refresh } = useFetch(
	"https://fakestoreapi.com/products"
);
console.log(data.value);
</script>
<template>
	<div class="dark">
		<main>
			<div class="wrapper p-6 border-dashed border-slate-500">
				<div class="p-4 shadow bg-slate-200">
					<h2>PRODUCTS</h2>
					<button>GO BACK</button>
				</div>
				<div class="mt-10 grid grid-cols-4 gap-5">
					<div
						v-for="el in data"
						to="/"
						class="w-full max-w-sm border rounded-lg shadow bg-gray-800 border-gray-700">
						<div class="bg-white m-5 rounded-xl">
							<img
								class="p-8 rounded-2xl w-full h-[300px] object-contain"
								:src="el.image"
								alt="product image" />
						</div>
						<div class="px-5 pb-5">
							<a href="#">
								<h5 class="text-xl font-semibold tracking-tight text-white">
									{{ el.title }}
								</h5>
							</a>
							<div class="flex items-center mt-2.5 mb-5">
								<svg
									v-for="i in Math.ceil(el.rating.rate)"
									aria-hidden="true"
									class="w-5 h-5 text-yellow-300"
									fill="currentColor"
									viewBox="0 0 20 20"
									xmlns="http://www.w3.org/2000/svg">
									<title>First star</title>
									<path
										d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"></path>
								</svg>
								<span
									class="text-xs font-semibold mr-2 px-2.5 py-0.5 rounded bg-blue-200 text-blue-800 ml-3"
									>{{ el.rating.rate }}</span
								>
							</div>
							<div class="flex items-center justify-between">
								<span class="text-2xl font-bold text-white"
									>${{ el.price }}</span
								>
								<nuxt-link
									:to="`/products/${el.id}`"
									class="text-white focus:ring-4 focus:outline-none font-medium rounded-lg text-sm px-5 py-2.5 text-center bg-blue-600 hover:bg-blue-700 focus:ring-blue-800">
									More ...
								</nuxt-link>
							</div>
						</div>
					</div>
				</div>
			</div>
		</main>
	</div>
</template>

<style scoped></style>
