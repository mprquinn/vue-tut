<template>
	<div class="users">
		<h1>Users</h1>
		<form v-on:submit="addUser">
			<input type="text" v-model="newUser.name" placeholder="Enter Name">
			<br>
			<input type="text" v-model="newUser.email" placeholder="Enter Email">
			<br>
			<input type="submit" value="Submit">
		</form>
		<ul>
			<li v-for="user in users">
				<input type="checkbox" class="toggle" v-model="user.contacted">
				<span :class="{contacted: user.contacted}">
					{{ user.name }}: {{ user.email }}
					<button v-on:click="deleteUser(user)">x</button>
				</span>
			</li>
		</ul>
	</div>
</template>

<script>
	export default {
		name: 'users',
		data() {
			return {
				users: [
					{
						name: 'Jane Doe',
						email: 'jdoe@gmail.com',
						contacted: false
					},
					{
						name: 'Steve Smith',
						email: 'ssmith@gmail.com',
						contacted: false
					},
					{
						name: 'Tom White',
						email: 'twhite@gmail.com',
						contacted: false
					},
				],
				newUser: {}
			}
		},
		methods: {
			addUser: function (e) {
				e.preventDefault();
				this.users.push({
					name: this.newUser.name,
					email: this.newUser.email,
					contacted: false
				});
			},
			deleteUser: function(user) {
				// e.preventDefault();
				this.users.splice(this.users.indexOf(user),1)
			}
		}
	}
</script>

<style scoped>
ul {
	margin-top: 3em;
}
li {
	list-style: none;
	width: 33%;
	margin: 1em auto;
	border: 1px solid #000;
	padding: 1em 0.33em;
	/*text-align: left;*/
	background: yellow;
}
.contacted {
	text-decoration: line-through;
	background: lightgreen;
}
</style>