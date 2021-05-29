<template>
  <div>
		<h1>Witaj w systemie zapisów na zajęcia</h1>
		<div v-if = "authenticatedEmail != ''">
			<h2>Witaj {{authenticatedEmail}}</h2>
			<button @click="logMeOut()">Wyloguj</button>
		</div>
		<div v-else>
			<h2>Zalogij się e-mailem</h2>
			<input type="text" v-model="email">
			<button @click="logMeIn()">Wchodzę</button>
		</div>		
  </div>
</template>

<script>
	data() {
		return {
			email: '',
			authenticatedEmail: ''
		};
	},
	methods: {
		logMeIn() {
			this.authenticatedEmail = this.email;
		},
		logMeOut() {
			this.authenticatedEmail = '';
			this.email = '';
		}
	}
};
</script>

<style>

</style>
