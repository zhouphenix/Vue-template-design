<template>
	<v-app id="inspire">
		<v-navigation-drawer v-model="drawer" clipped app fluid>
			<template v-slot:prepend>
				<v-list-item>
					<v-img src="./assets/logo.png"></v-img>
				</v-list-item>
			</template>

			<v-divider></v-divider>

			<v-list rounded dense>
				<v-list-item-group v-model="item" color="primary">
					<template v-for="(item, index) in items">
						<v-list-item :key="item.title">
							<v-list-item-icon>
								<v-icon>{{ item.icon }}</v-icon>
							</v-list-item-icon>

							<v-list-item-content>
								<v-list-item-title>{{ item.title }}</v-list-item-title>
							</v-list-item-content>
						</v-list-item>
						<v-divider v-if="index === 2" :key="index" class="mb-6"></v-divider>
					</template>


				</v-list-item-group>
			</v-list>

			<v-footer v-bind="localAttrs" :padless="true">
				<v-card tile width="100%" class="black lighten-1 text-center">

					<v-card-text class="white--text">
						—— 今日励志： 心有猛虎，细嗅蔷薇。
						{{ new Date().getFullYear() }} — <strong>Uni-Template</strong>
					</v-card-text>
				</v-card>
			</v-footer>
		</v-navigation-drawer>
		<v-app-bar app color="primary" dark clipped-left>
			<v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
			<div class="d-flex align-center">
				<v-img alt="Vuetify Logo" class="shrink mr-2" contain src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
				 transition="scale-transition" width="40" />

				<v-img alt="Vuetify Name" class="shrink mt-1 hidden-sm-and-down" contain min-width="100" src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
				 width="100" />
			</div>
			
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
			item: 0,
			items: [{
					title: '全部项目',
					icon: 'mdi-expand-all'
				},
				{
					title: '最近修改',
					icon: 'mdi-clock-time-four'
				},
				{
					title: '星标项目',
					icon: 'mdi-star-circle'
				},
				{
					title: '回收站',
					icon: 'mdi-trash-can'
				},
				{
					title: '个人版',
					icon: 'mdi-diamond'
				}
			],
		}),
		computed: {
			localAttrs() {
				return {
					absolute: true
				}
			},
		},
	}
</script>
