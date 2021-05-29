<template>
  <div>
		<h1>Witaj w systemie zapisów na zajęcia</h1>
		<div v-if = "authenticatedEmail != ''">
			
			<meeting-page></meeting-page>	
			<h2>Witaj {{authenticatedEmail}}</h2>			
			<button @click="logMeOut()">Wyloguj</button>
		</div>
		<div v-else>
			<login-form @login="logMeIn($event)" button-label="Wejdź"></login-form>
			<login-form @login="enter($event)" button-label="Wleć"></login-form>
			<login-form @login="enter($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
			<login-form @login="logMeIn($event)"></login-form>
		</div>	
		<meetings-page></meetings-page>		
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import MeetingPage from "./meetings/MeetingPage";


export default {
	components: {LoginForm, MeetingPage},
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
