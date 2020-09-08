<template>
  <div class="p-0" :class="{'pl-4': $vuetify.breakpoint.smAndDown}">
    <v-container fill-height fluid>
	  <v-row align="center"
	      justify="center"
	      >
	      <v-col cols="12" md="6" class="text-center ">
	      	<p  class="display-2 font-weight-bold mb-10">
	      		Get in touch
	      	</p>
	      	<p id="second">
	      		I'm currently looking for any new opportunities in software development, my inbox is always open. Whether you have a question or just want to say hi, I'll try my best to get back to you!
	      	</p>
	      	<div class="d-flex pt-10 justify-center">
    				<v-tooltip top
    					v-for="(contact, index) in contacts"
    					:key="index"
    				>
    					<template v-slot:activator="{ on, attrs }">
		    				<v-btn
		    					icon
		    					class="mr-5"
		    					v-bind="attrs"
				          		v-on="on"
		    					@click="redirect(contact.url)"
		    				>
		    					<v-icon>
		    						{{contact.icon}}
		    					</v-icon>
		    				</v-btn>
	    				</template>
	    				<span>{{contact.message}}</span>
    				</v-tooltip>
    			</div>
	      </v-col>
	  </v-row>
	</v-container>
  </div>
</template>
<script type="text/javascript">
  export default {
  	data () {
  		return {
  			contacts: [
  				{icon: 'mdi-whatsapp', message: "+27 62 283 6577", url: ''},
  				{icon: 'mdi-linkedin', message: "Check out my linkedin profile", url: 'https://www.linkedin.com/in/tom-havatyi-377a6b102/'},
  				{icon: 'mdi-email', message: 'havvtom@gmail.com', url: ''}
  			]
  		}
  	},
  	head () {
  		return {
  			title: 'Contact me'
  		}
  	},
  	methods: {
  		redirect (url) {
  			if(url){
  				window.open( url, '_blank')
  			}
  			return
  		}
  	}
  }
</script>

<style>
#second{
	color: #677380;
	letter-spacing: 1px;
	margin-bottom: 100px;
}
</style>