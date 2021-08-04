<template>
  <div class="p-0" :class="{'pl-4': $vuetify.breakpoint.smAndDown}" color="#1e3656">
    My projects which are currently on the web
    <v-row
    	v-for="(project, index) in projects"
    	:key="index"
    >
    	<v-col cols="12" md="8">
    		<v-container fill-height fluid>
          <!-- src="~/assets/images/joshhavv.jpg" -->
            <v-row align="center" justify="start">
                <v-img
                  :src="project.image"
                  lazy-src="https://picsum.photos/id/11/100/60"
                  aspect-ratio="1"
                  class="grey lighten-2 gray"
                  max-width="547"
                  max-height="307"
                >
                  <template v-slot:placeholder>
                    <v-row
                      class="fill-height ma-0"
                      align="center"
                      justify="center"
                    >
                      <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                    </v-row>
                  </template>
                </v-img>
            </v-row>
          </v-container>
    	</v-col>
    	<v-col cols="12" md="4">
    		<div>
    			<p class="flex-column myFont">Featured Project</p>
    			<p class="text-h3 title">{{project.title}}</p>
    			<p class="myFont">
    				{{project.description}}
    			</p>
    			<div class="d-flex pt-10">
    				<p class="mr-10 font-weight-thin"
    					v-for="(lang, index) in project.languages"
    					:key="index"
    				>
    					{{ lang }}
    				</p>
    			</div>
    			<div class="d-flex pt-10 justify-end" :class="{ 'justify-center' : $vuetify.breakpoint.smAndDown }">
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
		    						mdi-github
		    					</v-icon>
		    				</v-btn>
	    				</template>
	    				<span>Check out the github repository</span>
    				</v-tooltip>
    				<v-tooltip bottom>
    					<template v-slot:activator="{ on, attrs }">
		    				<v-btn
		    					icon
		    					v-bind="attrs"
				          		v-on="on"
		    					@click="redirect(project.websiteUrl)"
		    				>
								<svg 
									style="width:24px;height:24px" 
									viewBox="0 0 24 24"									
								>
								    <path fill="currentColor" d="M14,3V5H17.59L7.76,14.83L9.17,16.24L19,6.41V10H21V3M19,19H5V5H12V3H5C3.89,3 3,3.9 3,5V19A2,2 0 0,0 5,21H19A2,2 0 0,0 21,19V12H19V19Z" />
								</svg>    					
		    				</v-btn>
	    				</template>
	    				<span>Check out the website</span>
    				</v-tooltip>
    			</div>
    		</div>
    	</v-col>
    </v-row>
  </div>
</template>
<script type="text/javascript">
  export default {
  	data () {
  		return {
  			projects: [
  				{
  					title: 'Mathsnippets', 
  					description: 'Write your mathematics algebra notes in latex on the web.',
  					languages: ['Laravel', 'Tailwind', 'Nuxt.js'],
  					image: require('~/assets/images/mathsnippets.png'),
  					websiteUrl: 'http://mathsnippets.herokuapp.com/',
  					githubUrl: 'https://github.com/havvtom/Snippets-Client'
  				},
          {
            title: 'Jobs Portal', 
            description: 'Post jobs for fellow developers to apply directly',
            languages: ['Laravel', 'Tailwind', 'Nuxt.js'],
            image: require('~/assets/images/jobsportal.png'),
            websiteUrl: 'http://jobsclient.herokuapp.com',
            githubUrl: 'https://github.com/havvtom/jobsclient'
          }
  			]
  		}
  	},
  	head () {
  		return {
  			title: 'Projects'
  		}
  	},
  	methods: {
  		redirect (url) {
  			window.open( url, '_blank')
  		}
  	}
  }
</script>

<style scoped>
.myFont {
    font-family: 'Mansalva', cursive; 
    letter-spacing: 1px;
    color: #03fcec;
  }
 .title{
 	color: #03fcec;
 }
.gray{
    filter: grayscale(100%);
    filter: sepia(100%);
    transition: .3s ease-in-out;
  }
 .gray:hover{
    filter: grayscale(0);
    filter: sepia(0);
  }
</style>