<template>
  <div>
    <div style="text-align: center; margin: 5rem; " >
      <router-link to="/location" style="border-radius: 1rem; margin: 2rem; background-color: yellow; padding: 2rem; font-size: 2rem; color: black; text-decoration: none;">Location</router-link>
      <router-link to="/"  style="border-radius: 1rem; margin: 2rem;  background-color: yellow; padding: 2rem; font-size: 2rem; color: black; text-decoration: none;">Home</router-link>
    </div>
    
    <Navbar></Navbar> 
    
   
    <router-view /> 
    
    
  </div>
</template>
<script setup>

import Navbar from './components/Nabar.vue'



</script>

<style>



</style>