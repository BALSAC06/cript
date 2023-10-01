<template>
    <Navbar></Navbar> 
    <header style="text-align: center;font-family:cursive; font-size: 6rem; color: gold; padding-top: 1.5rem;
    ">
    Información
    </header>

   
    <router-view /> 
  
</template>
<script setup>

import Navbar from './components/Nabar.vue'



</script>

<style>

body{
  background-color: rgb(143, 139, 139);
  width: 1600px;
  height: 10rem;
  align-content:center;
}

</style>