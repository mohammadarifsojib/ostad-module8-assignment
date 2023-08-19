<script setup>
	import { ref } from "vue";
	import ChildComponent from "./ChildComponent.vue";
	const message = ref("Hello World from Parent Component");
	const childMessage = ref("");
	const showEmitMsg = (msg) => {
		childMessage.value = msg;
	};
</script>
<template>
	<div
		class="border border-gray-500 p-5 lg:p-20 flex flex-col gap-5 justify-center items-center"
	>
		<h1 class="text-3xl font-bold">Parent Component</h1>
		<h2 class="flex flex-col lg:block">
			<span class="text-sky-500 font-semibold"
				>Message from Child Component by Emit:
			</span>
			<span class="text-red-500 underline underline-offset-8">{{
				childMessage
			}}</span>
		</h2>
	</div>
	<div class="mt-5">
		<ChildComponent :message="message" @message-emitted="showEmitMsg" />
	</div>
</template>
<style scoped></style>
