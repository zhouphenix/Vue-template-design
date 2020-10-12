<template>
	<v-app id="inspire">
		<v-navigation-drawer v-model="drawer" clipped app>
			<template v-slot:prepend>
				<v-list-item>
					<v-img src="./assets/logo.png"></v-img>
				</v-list-item>
			</template>

			<v-divider></v-divider>

			<v-list dense>
				<v-list-item v-for="item in items" :key="item.title">
					<v-list-item-icon>
						<v-icon>{{ item.icon }}</v-icon>
					</v-list-item-icon>

					<v-list-item-content>
						<v-list-item-title>{{ item.title }}</v-list-item-title>
					</v-list-item-content>
				</v-list-item>
			</v-list>
		</v-navigation-drawer>
		<v-app-bar app color="primary" dark clipped-left>
			<v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
			<div class="d-flex align-center">
				<v-img alt="Vuetify Logo" class="shrink mr-2" contain src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
				 transition="scale-transition" width="40" />

				<v-img alt="Vuetify Name" class="shrink mt-1 hidden-sm-and-down" contain min-width="100" src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
				 width="100" />
			</div>

			<v-spacer></v-spacer>

			<v-btn href="https://github.com/vuetifyjs/vuetify/releases/latest" target="_blank" text>
				<span class="mr-2">Latest Release</span>
				<v-icon>mdi-open-in-new</v-icon>
			</v-btn>
		</v-app-bar>

		<v-main>

			<HelloWorld />
		</v-main>
	</v-app>
</template>

<script>
	import HelloWorld from './components/HelloWorld';

	export default {
		name: 'App',

		components: {
			HelloWorld,
		},

		data: () => ({
			drawer: null,
			items: [{
					title: 'Home',
					icon: 'mdi-home-city'
				},
				{
					title: 'My Account',
					icon: 'mdi-account'
				},
				{
					title: 'Users',
					icon: 'mdi-account-group-outline'
				},
			],
		}),
	};
</script>
