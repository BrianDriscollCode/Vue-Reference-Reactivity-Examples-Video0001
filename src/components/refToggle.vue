<template>
    <main>
		<h1 v-if="isInPool"> You are in the pool! </h1>
		<h1 v-if="!isInPool"> You are waiting to jump... </h1>

		<button @click="jump"> {{ isInPool ? "Get out of pool": "Jump into the pool" }} </button>
	</main>
</template>

<script setup>
import { ref } from "vue";

let isInPool = ref(false);

function jump() {
	isInPool.value = !isInPool.value;
}
</script>

<style scoped>

main {
	padding: 2em;
}

</style>
