<template>
  <div class="p-0" :class="{'pl-4': $vuetify.breakpoint.smAndDown}" color="success">
    <p id="first">
      Hi, my name is 
    </p>
    <p class="display-3 font-weight-bold" id="second">
      Tom Havatyi.
    </p>
    <p id="third" class="display-3 font-weight-bold">
      I love building things for the web.
    </p>
    <v-row>
      <v-col id="fourth" md="8" class="mt-16 font-weight-thin">
        I am a self taught software engineer based in Johannesburg. Software engineering started as a hobby and has now become a passion. The challenges it poses got me hooked.         
      </v-col>
    </v-row>
    <v-row class="pt-10">
      <div class="mr-5">
        <p id="fifth" class="display-2 mb-0 pl-3" :class=" { 'display-1' : $vuetify.breakpoint.smAndDown } ">About Me</p>
      </div>
      <div class="d-flex align-center">
        <div class="line" v-bind:style="{ width: maxWidth }"></div>
      </div>
    </v-row>
    <v-row>
      <v-col cols="12" md="6">
        <div class="myFont mb-5">
          Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. 
        </div>
        <p class="myFont">Listed below are the technologies I am familiar with:</p>
        <div>
          <v-row>
            <v-col>
              <ul class="myFont font-weight-thin">
                <li>Nuxt.js</li>
                <li>Vue.js</li>
                <li>Laravel</li>
              </ul>
            </v-col>
            <v-col>
              <ul class="myFont">
                <li>Tailwind</li>
                <li>Vuetify</li>
                <li>CSS</li>
              </ul>
            </v-col>
          </v-row>
        </div>
      </v-col>
      <v-col cols="12" md="6">
         <v-container fill-height fluid>
          <!-- src="~/assets/images/joshhavv.jpg" -->
            <v-row align="center" justify="center">
                <v-img
                  :src="require('~/assets/images/joshhavv.jpg')"
                  lazy-src="https://picsum.photos/id/11/100/60"
                  aspect-ratio="1"
                  class="grey lighten-2 gray"
                  max-width="300"
                  max-height="200"
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
    </v-row>
  </div>
</template>
<script type="text/javascript">
  export default {
    head () {
      return {
        title: 'HavvTom'
      }
    },
    computed: {
      maxWidth () {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs': return '150px'
            break;
          case 'sm': return '300px'
            break;
          case 'md': return '300px'
            break;
          case 'lg': return '400px'
            break;
          case 'xlg': return '500px'
            break;
        }
      }
    }

  }
</script>

<style scoped>
  .myFont {
    font-family: 'Mansalva', cursive; 
    letter-spacing: 1px;
    color: #a6a195;
  }
  .line{
      color: #a6a195;
      border-bottom: 0.5px solid white;
      position: absolute;
    }
  #first{
    font-family: 'Mansalva', cursive;
    font-size: 20px;
    color: #34ebdb;
  }
  #third{
    margin-top: 40px;
    color: #8c968f;
  }
  #fourth{
    margin-bottom: 80px;
    letter-spacing: 1px;
    font-family: 'Mansalva', cursive;
    color: #a6a195;
  }
  #fifth{
    color: #a6a195;
  }
  .gray{
    filter: grayscale(100%);
    transform: scale(1);
    transition: .3s ease-in-out;
  }
  .gray:hover{
    filter: grayscale(0);
    transform: scale(1.3);
  }
  ul {
    position: relative;
    list-style: none;
  }

  li::before {
    content: '➣';
    position: absolute;
    left: 0;
  }
</style>