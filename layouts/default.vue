<template>
  <v-app class="white">
    <TheNavbar/>

      <v-container>
        <nuxt />
      </v-container>


    <v-footer id="first"
    >
      <v-container>
        <div id="second" class="text-center mb-0">
          <p>Designed and built by Tom Havatyi</p>
          <p class="">&copy; {{ new Date().getFullYear() }} havvtom@gmail.com</p>
        </div>
      </v-container>      
    </v-footer>
  </v-app>
</template>

<script>
import TheNavbar from '@/components/TheNavbar'
export default {
  data () {
    return {
      
    }
  },
  components: {
    TheNavbar
  }
}
</script>

<style scoped>
  .v-application {
    background-color: #1e3656;
  }
  #first{
    margin-top: 50px;
    background-color: #1e3656;
  }
  #second {
    font-size: 12px;
  }
  #second :hover{
    color: #a6a195;
  }
</style>


