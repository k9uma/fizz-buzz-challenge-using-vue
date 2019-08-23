<template>
  	<div id="app">
    	<b-card
      		title="FizzBuzz Challenge Using Vue"
      		sub-title="Simple application of the fizz buzz challenge using Vue.js"
		>
			<b-card-text>
				<b-list-group>
					<b-list-group-item v-if="!items.length">No Data Yet</b-list-group-item>
					<b-list-group-item v-for="item in items" v-bind:key="item.id">{{ item.message }}</b-list-group-item>
				</b-list-group>
			</b-card-text>
			<b-button variant="outline-primary" v-on:click="runCheck()">Check</b-button>
   		</b-card>
  	</div>
</template>

<script>
const defaultValue = 100;
export default {
  	name: "app",
  	data() {
		return {
			items: []
	};
},
methods: {
	runCheck: function() {
		this.items = []
		for (let index = 1; index <= defaultValue; index++) {
			if (index % 3 === 0 && index % 5 === 0) {
				this.addToArray(index, "FizzBuzz");
			} else if (index % 3 == 0) {
				this.addToArray(index, "Fizz");
			} else if (index % 5 == 0) {
				this.addToArray(index, "Buzz");
			} else {
				this.addToArray(index, index);
			}
		}
		},
		addToArray: function(index, message) {
			this.items.push({
				id: index,
				message: message
			});
    	}
  	}
};
</script>

<style>
</style>
