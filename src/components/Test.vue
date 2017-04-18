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
		<button v-on:click="greet('Hello World')">Say Greeting</button><br>
		<input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
		<hr>
		<label>First Name</label>
		<input type="text" v-model="user.firstName" placeholder="First Name"><br>
		<label>last Name</label>
		<input type="text" v-model="user.lastName" placeholder="Last Name">
		<h3>{{fullName}}</h3>
		<h4>{{message}}</h4>
	</div>
</template>

<script>
	export default {
		name: 'test',
		props: {
			message: {
				type: String,
				default: 'Hell World'
			}
		},
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
			},
			pressKey: function (e) {
				console.log(e.target.value);
			},
			enterHit: function (e) {
				console.log('you hit enter');
			}
		},
		computed: {
			fullName: function () {
				return this.user.firstName + ' ' + this.user.lastName;
			}
		}
	}
</script>

<style scoped>
</style>