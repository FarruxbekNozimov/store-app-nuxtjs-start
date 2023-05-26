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
			</div>
		</main>
	</div>
</template>

<script setup></script>

<style scoped></style>
