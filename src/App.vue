<template>
    <main>

        <button @click="changeExample('data')"> Show Reactive Data </button>
		<button @click="changeExample('state')"> Show Reactive State </button>
		<button @click="changeExample('basics')"> Show Ref Basics </button>
		<button  @click="changeExample('toggle')"> Show Ref Toggle </button>

		<reactiveData v-if="component.reactiveData"/>
		<reactiveState v-if="component.reactiveState"/>
		<refBasics v-if="component.refBasics"/>
		<refToggle v-if="component.refToggle"/>
	</main>
</template>

<script setup>
import { reactive } from "vue";
import reactiveData from "@/components/reactiveData.vue";
import reactiveState from "@/components/reactiveState.vue";
import refBasics from "@/components/refBasics.vue";
import refToggle from "@/components/refToggle.vue";

let component = reactive({
	reactiveData: false,
	reactiveState: false,
	refBasics: true,
	refToggle: false
})

function changeExample(state) {
    if (state === "data")
	{
        component.reactiveData = true;
		component.reactiveState = false;
		component.refBasics = false;
		component.refToggle = false;
	}
	else if (state === "state")
	{
		component.reactiveData = false;
		component.reactiveState = true;
		component.refBasics = false;
		component.refToggle = false;
	}
	else if (state === "basics")
	{
		component.reactiveData = false;
		component.reactiveState = false;
		component.refBasics = true;
		component.refToggle = false;
	}
	else if (state === "toggle")
	{
		component.reactiveData = false;
		component.reactiveState = false;
		component.refBasics = false;
		component.refToggle = true;
	}
	console.log(component);
}

console.log(component);

</script>

<style scoped>
main {
	padding: 2em;
}
button {
	margin-left: 1em;
}
</style>
