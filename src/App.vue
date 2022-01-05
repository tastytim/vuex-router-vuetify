<template>
  <v-app class="app">
    
    <Navbar></Navbar>
    <router-view></router-view>
    
  </v-app>
  
</template>

<script>
import Navbar from './components/Navbar.vue';

export default {
  components: { Navbar },
  name: 'App',

};
</script>
<style >
  .app{
      margin: 0;
      padding: 0;
      box-sizing: border-box;
  }
</style>
