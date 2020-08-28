<template>
	<nav>
	<v-app-bar color="#1e3656" flat height="150">		
		<v-container>
			<v-row>
				<v-col>
					<svg version="1.0" xmlns="http://www.w3.org/2000/svg"
						 width="40px" height="40px" viewBox="0 0 200.000000 200.000000"
						 preserveAspectRatio="xMidYMid meet">

						<g transform="translate(0.000000,200.000000) scale(0.100000,-0.100000)"
						fill="#34ebbd" stroke="none">
						<path d="M100 1000 l0 -900 165 0 165 0 0 370 0 370 570 0 570 0 0 -370 0
						-370 165 0 165 0 0 900 0 900 -165 0 -165 0 0 -370 0 -370 -570 0 -570 0 0
						370 0 370 -165 0 -165 0 0 -900z"/>
						</g>
					</svg>
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
					<v-btn 
						class="ml-2" 
						outlined 
						color="teal"
						@click="openPdf"
					>
						Resume
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

			<v-btn 
				class="ma-16" 
				outlined 
				color="teal"
				@click="openPdf"
			>
				my Resume
			</v-btn>
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
					{ title: 'Contact Me', icon: 'mdi-email', url: '/contact'},
				]
			}
		},
		methods: {
			closeDrawer () {
				setTimeout( () => this.drawer = false, 500)
			},
			openPdf () {
				window.open('sample.pdf', '_blank')
			}
		}
	}
</script>

<style>
  .myFont {
    font-family: 'Mansalva', cursive; 
  }
</style>

