<template>
    <main>
		<input v-model="userInput" />
        <button @click="submitForm"> Submit form </button>
		<p class="errorStatement" v-if="componentState.inProgress"> Please fill out form </p>
		<p class="errorStatement" v-if="componentState.error"> Needs to be longer than 2 characters </p>
		<p class="successStatement" v-if="componentState.success"> Success! </p>
	</main>
</template>

<script setup>
import { ref, reactive } from "vue";

let userInput = ref("");

let componentState = reactive({
	inProgress: true,
	error: false,
	success: false
})

function submitForm() {
	console.log(userInput.value)
	if (userInput.value.length > 2)
	{
        componentState.inProgress = false;
		componentState.error = false;
		componentState.success = true;
	}
	else if (userInput.value.length <= 2 && userInput.value.length > 0)
	{
        componentState.inProgress = false;
		componentState.error = true;
		componentState.success = false;
	}
	else
	{
		componentState.inProgress = true;
		componentState.error = false;
		componentState.success = false;
	}
}

</script>

<style scoped>

main {
	padding: 2em;
}

.errorStatement {
	color: red;
}

.successStatement {
	color: green;
}

</style>
