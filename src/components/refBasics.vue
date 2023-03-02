<template>
    <main>
		<h1> {{ title }} </h1>

		<button @click="changeTitle"> Change Title </button>
	</main>
</template>

<script setup>
import { ref } from "vue"; //import ref

let title = ref("Reactivity Explained"); // wrap value with ref

function changeTitle() {
	title.value = "Reactivity Works"; //use .value syntax
}

</script>

<style scoped>

main {
	padding: 2em;
}

</style>