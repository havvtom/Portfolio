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
        I am a self taught software engineer based in Johannesburg, holding an honours degree in Chemical Engineering. Software engineering started as a hobby and has now become a passion. The challenges it poses got me hooked.         
      </v-col>
    </v-row>
    <v-row class="pt-10">
      <div class="mr-5">
        <p class="display-2 mb-0 pl-3" :class=" { 'display-1' : $vuetify.breakpoint.smAndDown } ">About Me</p>
      </div>
      <div class="d-flex align-center">
        <div class="line" v-bind:style="{ width: maxWidth }"></div>
      </div>
    </v-row>
  </div>
</template>
<script type="text/javascript">
  export default {
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

<style>
  .line{
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
  }
</style>