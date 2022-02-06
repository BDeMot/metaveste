<template>
<v-container fill-height fluid class='d-flex flex-column align-stretch justify-center'>

	<v-card
		class = 'pa-4'
		outlined
	>
		<v-form
			ref='form'
			v-model='valid'
		>
			<v-text-field
				v-model='user'
				:counter='20'
				:rules='userRules'
				label='Pseudo'
				outlined
				rounded
				required
			></v-text-field>

			<v-text-field
				v-model='email'
				:rules='emailRules'
				label='E-mail'
				outlined
				rounded
				required
			></v-text-field>

			<v-text-field
				v-model='password'
				:append-icon='show1 ? "mdi-eye" : "mdi-eye-off"'
				:rules='[passwordRules.required, passwordRules.min]'
				:type='show1 ? "text" : "password"'
				name='input-10-1'
				label='Mot de passe'
				hint='Minimum 8 caractères'
				counter
				outlined
				rounded
				@click:append='show1 = !show1'
			></v-text-field>

			<v-divider class='mb-6'>

			</v-divider>

			<v-btn
				:disabled='!valid'
				color='success'
				class='mr-4'
				@click='validate'
			>
				Validate
			</v-btn>

			<v-btn
				color='error'
				class='mr-4'
				@click='reset'
			>
				Reset Form
			</v-btn>

		</v-form>
	</v-card>
</v-container>
</template>

<script>
export default {
	name: "landingPage",
	
	data() {
		return {
			valid: false,
			show1: false,
			user: '',
			userRules: [
				v => !!v || 'Name is required',
				v => (v && v.length <= 20) || 'Name must be less than 10 characters',
			],
			email: '',
			emailRules: [
				v => !!v || 'E-mail is required',
				v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
			],
			password: '',
			passwordRules: {
				required: value => !!value || 'Required.',
				min: v => v.length >= 8 || 'Min 8 characters'
			},
		}
	},
	methods: {
		validate () {
			this.$refs.form.validate()
			alert(`identifiants : ${this.user} , ${this.email}, ${this.password}`)
		},
		reset () {
			this.$refs.form.reset()
		}
	}
}
</script>
