<template>
  <div>
    
    <Navbar></Navbar>
    <router-view />
  </div>
</template>
<script setup>

import Navbar from './components/Nabar.vue'
import Home from './views/Home.vue'

</script>
