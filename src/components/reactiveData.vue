<template>
    <main>
		<h1> Title </h1>
        <ul >
			<li v-for="(item, name) in employee" :key="name"> {{ name }}: {{ item }} </li>
		</ul>

		<button @click="changeEmployee"> Change Employee </button>
	</main>
</template>
<!-- 1. Make name reactive -->
<!-- 2. Add an event handler -->

<script setup>
import { ref, reactive } from "vue";

let allEmployees = [
	{
    name: "Sheila",
	birthdate: "08/20/2000",
	salary: 62000,
	department: "marketing",
	position: "Social Media Manager"
    },
	{
    name: "Bob",
	birthdate: "08/20/2002",
	salary: 52000,
	department: "customer service"
    }
];

let employee = reactive(allEmployees[0])

function changeEmployee() {
	//Object.assign(employee, allEmployees[1]);
	for (let name in employee) {
        employee[name] = allEmployees[1][name];
	}
}

</script>
<style scoped>

main {
	padding: 2em;
}

</style>