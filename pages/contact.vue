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
	      		Although I'm not currently looking for any new opportunities, my inbox is always open. Whether you have a question or just want to say hi, I'll try my best to get back to you!
	      	</p>
	      	<div class="d-flex pt-10 justify-center">
    				<v-tooltip top>
    					<template v-slot:activator="{ on, attrs }">
		    				<v-btn
		    					icon
		    					class="mr-5"
		    					v-bind="attrs"
				          		v-on="on"
		    					@click="redirect(project.githubUrl)"
		    				>
		    					<v-icon>
		    						mdi-facebook
		    					</v-icon>
		    				</v-btn>
	    				</template>
	    				<span>We can be friends on fbk</span>
    				</v-tooltip>
    				<v-tooltip top>
    					<template v-slot:activator="{ on, attrs }">
		    				<v-btn
		    					icon
		    					v-bind="attrs"
				          		v-on="on"
		    					@click="redirect(project.websiteUrl)"
		    				>
								<v-icon>
									mdi-whatsapp
								</v-icon>   					
		    				</v-btn>
	    				</template>
	    				<span>+27 62 283 6577</span>
    				</v-tooltip>
    			</div>
	      </v-col>
	  </v-row>
	</v-container>
  </div>
</template>
<script type="text/javascript">
  export default {

  }
</script>

<style>
#second{
	color: #677380;
	letter-spacing: 1px;
	margin-bottom: 100px;
}
</style>