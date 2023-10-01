<template>


    <h2> PERSONAJES</h2>
  <div class="body">
    <div style="" class="box">
        <section  style="padding-bottom: 1rem; font-family:cursive ;padding-top:1rem ; display: block; text-align: center; margin: 1rem; color :black; border: solid gold 2px;" v-for="value in character" >

            <div class="content">
                <img v-bind:src="value.image" alt="" width="150" height="150" >
            
                <div style="padding-top: 1.5rem;">    
                    {{ value.name }}
                </div>

                <div style="padding-top: 1rem;">
                    {{value.type }}
                
                </div>
            </div>
        </section>
    </div>
  </div>
</template>

<script setup>

import { ref, onMounted } from 'vue'
import axios from 'axios'

onMounted(() => {
    getCharacter(); 
})

const character= ref(null);

const getCharacter= async()=>{
    await axios.get('https://rickandmortyapi.com/api/character')

    .then((resolve)=> {
        character.value=resolve.data.results
    }).catch((error)=>{
        console.log(error);
    })

}

</script>

<style scoped>

.body{
    background-image: url(../c137.webp);
    align-items: center;
    align-content: center;

}
.box{
    
    display: grid;
    grid-template-columns: 360px 360px 360px 360px;
    align-items: center;
    padding: 1rem;
    margin: 0 auto;
}
.content{
    padding: 10px;
    width: 70%;
    align-content: center;

}
h2{
    font-size: 5rem;
    background-color: gold;
    font-family: cursive;
}
@media (max-width: 800px) {
 
}

@media (min-width: 800px) and (max-width: 991px) {
 
}

@media (min-width: 1000px) {
 
}


</style>