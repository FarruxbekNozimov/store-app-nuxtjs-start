<template>
	<div>
		<header>
			<nav
				class="border-gray-200 px-4 lg:px-6 py-4 bg-gray-800/80 fixed w-screen">
				<div
					class="flex flex-wrap justify-between items-center mx-auto max-w-screen-xl">
					<nuxt-link to="/" class="flex items-center logo">
						<span
							class="self-center text-xl font-semibold whitespace-nowrap text-yellow-500 mr-1"
							>FAKE</span
						>
						<span
							class="self-center text-xl font-semibold whitespace-nowrap text-white">
							STORE
						</span>
					</nuxt-link>
					<div
						class="hidden justify-between items-center w-full lg:flex lg:w-auto lg:order-1"
						id="mobile-menu-2">
						<ul
							class="flex flex-col mt-4 font-medium lg:flex-row lg:space-x-8 lg:mt-0">
							<li>
								<router-link
									to="/"
									class="block py-2 pr-4 pl-3 rounded bg-primary-700 lg:bg-transparent lg:text-primary-700 lg:p-0 text-white"
									aria-current="page">
									Home
								</router-link>
							</li>
							<li>
								<router-link
									to="/products"
									class="block py-2 pr-4 pl-3 rounded bg-primary-700 lg:bg-transparent lg:text-primary-700 lg:p-0 text-white"
									aria-current="page">
									Products
								</router-link>
							</li>
							<li>
								<router-link
									to="/about"
									class="block py-2 pr-4 pl-3 rounded bg-primary-700 lg:bg-transparent lg:text-primary-700 lg:p-0 text-white"
									aria-current="page">
									About
								</router-link>
							</li>
							<li>
								<router-link
									to="/contact"
									class="block py-2 pr-4 pl-3 rounded bg-primary-700 lg:bg-transparent lg:text-primary-700 lg:p-0 text-white"
									aria-current="page">
									Contact
								</router-link>
							</li>
						</ul>
					</div>
				</div>
			</nav>
		</header>
	</div>
</template>

<script setup></script>

<style scoped>
.router-link-exact-active {
	font-weight: 800;
	text-decoration: underline;
}
.logo {
	text-decoration: none;
}
</style>
