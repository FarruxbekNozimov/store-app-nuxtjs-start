<script setup>
const { id } = useRoute().params;

const { data } = await useFetch(`https://fakestoreapi.com/products/${id}`);

if (!data.value) {
	throw createError({
		errorMessage: "Product not found",
		statusCode: 404,
	});
}
</script>

<template>
	<div class="dark">
		<main>
			<div class="wrapper p-6 border-dashed border-slate-500">
				<div
					class="p-2 flex items-center justify-between shadow bg-slate-600 text-white rounded-xl">
					<h2 class="px-4 py-2">PRODUCTS {{ id }}</h2>
					<button
						@click="useRouter().go(-1)"
						class="px-4 py-2 bg-red-500 rounded-xl">
						GO BACK
					</button>
				</div>
				<div class="mt-10 w-full">
					<section
						class="text-gray-700 body-font overflow-hidden bg-gray-800 rounded-xl">
						<div class="container px-5 py-5 mx-auto">
							<div class="lg:w-full mx-auto flex flex-wrap">
								<img
									alt="ecommerce"
									class="lg:w-1/2 w-full h-[100vh] object-contain object-center rounded-xl bg-white"
									:src="data.image" />
								<div class="lg:w-1/2 w-full lg:pl-10 lg:py-6 mt-6 lg:mt-0">
									<h2
										class="mb-2 text-sm title-font text-gray-100 tracking-widest">
										{{ data?.category.toUpperCase() }}
									</h2>
									<h1
										class="text-slate-200 text-3xl title-font font-medium mb-1">
										The Catcher in the Rye
									</h1>
									<div class="flex items-center mb-4 gap-20">
										<span class="flex items-center">
											<svg
												v-for="i in Math.ceil(data?.rating?.rate)"
												fill="currentColor"
												stroke="currentColor"
												stroke-linecap="round"
												stroke-linejoin="round"
												stroke-width="2"
												class="w-4 h-4 text-red-500"
												viewBox="0 0 24 24">
												<path
													d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"></path>
											</svg>
											<svg
												v-for="i in Math.floor(5 - data?.rating?.rate)"
												fill="none"
												stroke="currentColor"
												stroke-linecap="round"
												stroke-linejoin="round"
												stroke-width="2"
												class="w-4 h-4 text-red-500"
												viewBox="0 0 24 24">
												<path
													d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"></path>
											</svg>
											<span class="text-gray-600 ml-3"
												>{{ data?.rating?.count }} Reviews</span
											>
										</span>
										<div class="flex">
											<span
												class="title-font font-medium text-xl text-slate-200"
												>${{ data?.price }}</span
											>
										</div>
									</div>
									<p class="leading-relaxed text-gray-400">
										{{ data.description }}
									</p>
								</div>
							</div>
						</div>
					</section>
				</div>
			</div>
		</main>
	</div>
</template>

<style scoped></style>
