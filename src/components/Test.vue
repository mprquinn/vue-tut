<template>
	<div class="test">
		<h1>{{title}}</h1>
		<input type="text" v-model="title"><br>
		<p>
			Welcome, 
			<span v-if="showName">{{user.firstName}}</span>
			<span v-else>Anonymous</span>
		</p>
		<ul>
			<li v-for="item in items">
				{{item.title}}
			</li>
		</ul>
		<button v-on:click="greet('Hello World')">Say Greeting</button>
	</div>
</template>

<script>
	export default {
		name: 'test',
		data() {
			return {
				title: 'Hello World',
				user: {
					firstName: 'Jane',
					lastName: 'Doe'
				},
				showName: true,
				items: [
					{title: 'An Item'},
					{title: 'A Second Item'},
					{title: 'A Third Item'}
				],
			}
		},
		methods: {
			greet: function (greeting) {
				alert(greeting);
			}
		}
	}
</script>

<style scoped>
</style>