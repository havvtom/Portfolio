<template>
	<nav>
	<v-app-bar color="#1e3656" flat height="150">		
		<v-container>
			<v-row>
				<v-col>
					H-Logo
				</v-col>
				<v-col class="myFont d-none d-lg-flex d-xl-flex justify-end">
					<v-btn text 
						v-for="(link, index) in items"
						:key="index"
						class="font-weight-light text-capitalize ml-2" 
						color="#f5f5f5"
						nuxt
						:to="link.url"
					>
						{{ link.title }}
					</v-btn>
					
				</v-col>
				<v-btn text class="d-lg-none d-xlg-none" @click="drawer = !drawer">
					<v-icon>
						mdi-menu
					</v-icon>
				</v-btn>
			</v-row>
		</v-container>
	</v-app-bar>
	<v-navigation-drawer
			app
	    	color="#1e3656"
	    	class="d-lg-none d-xlg-none"
	    	v-model="drawer"
	    >
	    	<v-list>
		        <v-list-item
					v-for="(link, index) in items"
					:key="index"
					:to="link.url"
					nuxt
					@click="closeDrawer"
					class="myFont"
				>
					<v-list-item-icon>
			           <v-icon class="grey--text">
			           		{{link.icon}}
			         	</v-icon>
			        </v-list-item-icon>
					<v-list-item-content>
						<v-list-item-title class="grey--text">
							{{link.title}}
						</v-list-item-title>
					</v-list-item-content>
				</v-list-item>
			</v-list>
		</v-navigation-drawer>
	</nav>
</template>

<script type="text/javascript">
	export default {
		data () {
			return {
				drawer: false,
				items: [
					{ title: 'Projects', icon: 'mdi-folder', url: '/projects'},
					{ title: 'About', icon: 'mdi-face', url: '/'},
					{ title: 'Contact', icon: 'mdi-email', url: '/contact'},
					{ title: 'Resume', icon: '', url: '/resume'},
				]
			}
		},
		methods: {
			closeDrawer () {
				setTimeout( () => this.drawer = false, 500)
			}
		}
	}
</script>

<style>
  .myFont {
    font-family: 'Mansalva', cursive; 
  }
</style>

