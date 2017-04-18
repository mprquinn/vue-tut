<template>
	<div class="test">
		<h1>{{title}}</h1>
		<p>
			Welcome, {{user.firstName}}
		</p>
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
				active: true
			}
		}
	}
</script>

<style scoped>
</style>