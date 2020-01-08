<template>
	<nav>
		<v-toolbar flat>
			<v-app-bar-nav-icon
				class="grey--text"
				@click="drawer = !drawer"
			></v-app-bar-nav-icon>
			<v-toolbar-title class="text-uppercase grey--text">
				<span class="font-weight-light">TODO</span>
				<span>Ninja</span>
			</v-toolbar-title>
			<v-spacer></v-spacer>

			<template>
				<div class="text-center">
					<v-menu offset-y>
						<template v-slot:activator="{ on }">
							<v-btn dark v-on="on" text color="grey">
								<v-icon text>mdi-chevron-down</v-icon>Menu
							</v-btn>
						</template>
						<v-list>
							<v-list-item
								v-for="link in links"
								:key="link.text"
								router
								:to="link.route"
							>
								<v-list-item-title>{{ link.text }}</v-list-item-title>
							</v-list-item>
						</v-list>
					</v-menu>
				</div>
			</template>

			<v-btn text color="grey">
				<span>Sign Out</span>
				<v-icon right>mdi-exit-to-app</v-icon>
			</v-btn>
		</v-toolbar>

		<v-navigation-drawer
			v-model="drawer"
			app
			temporary
			absolute
			class="purple accent-4"
		>
			<v-layout column align-center>
				<v-flex class="mt-5">
					<v-avatar size="85">
						<v-img src="/avatar-1.png"></v-img>
					</v-avatar>
					<p class="white--text subheading mt-1">The Net Ninja</p>
				</v-flex>
				<v-flex class="mt-4 mb-3">
					<Popup />
				</v-flex>
			</v-layout>
			<v-list>
				<v-list-item
					v-for="link in links"
					:key="link.text"
					router
					:to="link.route"
				>
					<v-list-item-action>
						<v-icon class="white--text">{{ link.icon }}</v-icon>
					</v-list-item-action>
					<v-list-item-content>
						<v-list-item-title id="link-active" class="white--text">{{
							link.text
						}}</v-list-item-title>
					</v-list-item-content>
				</v-list-item>
			</v-list>
		</v-navigation-drawer>
	</nav>
</template>

<script>
import Popup from "./popup";

export default {
	components: {
		Popup
	},
	data() {
		return {
			drawer: false,
			links: [
				{ icon: "mdi-view-dashboard-variant", text: "Dashboard", route: "/" },
				{ icon: "mdi-folder-account", text: "My Projects", route: "/projects" },
				{ icon: "mdi-account-group", text: "Team", route: "/team" }
			]
		};
	}
};
</script>

<style scoped>
.v-list-item--active {
	color: darkviolet !important;
}
</style>
