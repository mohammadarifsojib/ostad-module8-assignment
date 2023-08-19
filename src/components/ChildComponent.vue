<script setup>
	import { defineEmits } from "vue";
	defineProps(["message"]);
	const emit = defineEmits(["messageEmitted"]);
	const msgEmit = () => {
		emit("messageEmitted", "Hello World from Child Component");
	};
</script>
<template>
	<div class="border border-gray-500 p-20 flex flex-col gap-5">
		<h1 class="text-3xl font-bold text-center">Child Component</h1>
		<h2 class="text-center">
			<span class="text-sky-500 font-semibold"
				>Message from Parent Component by Props:
			</span>
			<span class="text-red-500 underline underline-offset-8">{{
				message
			}}</span>
		</h2>
		<button
			@click="msgEmit"
			class="bg-sky-500 rounded-lg w-1/6 mx-auto py-2 border border-sky-600 text-white hover:bg-transparent hover:text-sky-600 transition-all"
		>
			Click Me
		</button>
	</div>
</template>
<style scoped></style>
