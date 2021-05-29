<template>
  <div>
		<h1>Witaj w systemie zapisów na zajęcia</h1>
		<div v-if = "authenticatedEmail != ''">
			<h2>Witaj {{authenticatedEmail}}</h2>
			<button @click="logMeOut()">Wyloguj</button>
		</div>
		<div v-else>
			<login-form @login="logMeIn($event)"></login-form>
		</div>		
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
	components: {LoginForm},
	data() {
		return {

			authenticatedEmail: ''
		};
	},
	methods: {
		logMeIn(username) {
			this.authenticatedEmail = username;
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
