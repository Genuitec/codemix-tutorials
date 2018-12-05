<template>
	<div v-if="people" class="people">
		<md-table>
			<md-table-row>
				<md-table-head>Name</md-table-head>
				<md-table-head>Birth Year</md-table-head>
			</md-table-row>
			<md-table-row v-for="person in people" :key="person.name">
				<md-table-cell>
					{{person.name}}
				</md-table-cell>
				<md-table-cell>
					{{person.birth_year}}
				</md-table-cell>
			</md-table-row>
		</md-table>
		<md-button @click="updateNames(nextLink)">Next</md-button>
	</div>
	
</template>

<script>
import axios from "axios";
export default {
	name: 'StarWarsPeople',
	data() {
		return {
			people: null,
			nextLink: null
		}
	},

	created() {
		this.updateNames("https://swapi.co/api/people/?format=json");
	},

	methods: {
		updateNames(url) {
			axios.get(url).then(response => {
				this.nextLink = response.data.next;
				this.people = response.data.results;
			});
		}
	}
}
</script>

<style>
.people {
	text-align: left;
}
</style>
