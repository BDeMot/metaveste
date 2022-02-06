<template>
<v-app>
	<v-app-bar 
		app 
		flat 
		outlined
	>
		<div class='d-flex align-center'>
			<router-link to='/'>
				<h1 class='mb-0'>METAVESTE</h1>
			</router-link>
		</div>

		<v-spacer></v-spacer>

		<v-app-bar-nav-icon
			@click.stop='drawer = !drawer'
		>

		</v-app-bar-nav-icon>

	</v-app-bar>

	<v-navigation-drawer
		v-model='drawer'
		absolute
		temporary
	>
		<v-list
			nav
			dense
		>
			<v-list-item-group
				active-class='deep-purple--text text--accent-4'
			>
				<v-list-item>
					<v-list-item-title>Inscription</v-list-item-title>
				</v-list-item>

				<v-list-item>
					<v-list-item-title>Connexion</v-list-item-title>
				</v-list-item>

				<v-list-item>
					<v-list-item-title>Fizz</v-list-item-title>
				</v-list-item>

				<v-list-item>
					<v-list-item-title>Buzz</v-list-item-title>
				</v-list-item>
			</v-list-item-group>
		</v-list>
	</v-navigation-drawer>
	<v-main>
		<router-view />
	</v-main>
</v-app>
</template>

<script>
export default {
	name: "App",

	data: () => ({
		drawer: false
	}),
};
</script>

<style>
a {
    text-decoration: none;
	color: inherit;
}
</style>
