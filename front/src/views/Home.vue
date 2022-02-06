<template>
<v-container fill-height fluid class='d-flex flex-column justify-center'>
	
	<router-link to='/register'>
		<v-btn 
			outlined
			x-large
			color='primary' 
			width='80vw'
		>
			Inscription
		</v-btn>
	</router-link>

	<v-btn 
		x-large
		outlined
		width='80vw'
		class='mt-7'
	>
		Connexion
	</v-btn>
</v-container>
</template>

<script>
export default {
	name: "Home",
};
</script>
