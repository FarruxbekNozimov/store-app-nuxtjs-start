<script setup>
import { ref, onMounted } from "vue";
import Pusher from "pusher-js";
const username = ref("username");
const message = ref("");
const messages = ref([]);

const submit = () => {
	if (message.value.trim().length > 0) {
		messages.value.push({ text: message.value, name: username.value });
		console.log(messages.value);
	}
};
</script>
<template>
	<div class="dark">
		<main>
			<div class="wrapper p-6 border-dashed border-slate-500">
				<div class="p-4 shadow bg-slate-400 rounded-xl">
					<h2>CHAT PAGE</h2>
					<div>
						<div class="h-[50vh] overflow-y-auto items-end py-5">
							<div
								v-for="msg in messages"
								class="bg-sky-300 w-[50%] p-3 rounded-xl mb-2">
								<span>{{ msg.name }}</span>
								<p>{{ msg.text }}</p>
							</div>
						</div>
						<form @submit.prevent="submit" class="w-full flex h-[50px] gap-5">
							<input
								type="text"
								class="w-[95%] rounded-xl px-3"
								v-model="message" />
							<button class="bg-sky-500 w-[10%] rounded-xl">SEND</button>
						</form>
					</div>
				</div>
			</div>
		</main>
	</div>
</template>

<style scoped></style>
