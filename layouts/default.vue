<template>
  <v-app class="white">
    <TheNavbar/>

      <v-container>
        <nuxt />
      </v-container>


    <v-footer
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
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
</style>


