<template>
    
   
    <div class="contenedor">
        <section  style="padding-bottom: 1rem; padding-top:1rem ; display: block; text-align: center; margin: 1rem; color :green; border: solid green 4px;" v-for="value in character" >
        
        <div class="contendor_hijo">
            
            <div>
                
                {{ value.name }}
            </div>
        
            <div style="padding-top: 1.5rem;">    
                {{ value.type }}
            </div>

            <div style="padding-top: 1rem;">
                {{value.dimension }}
            
            </div>
        </div>


        </section>
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
    await axios.get('https://rickandmortyapi.com/api/location')

    .then((resolve)=> {
        character.value=resolve.data.results
    }).catch((error)=>{
        console.log(error);
    })

}

</script>

<style>

.contenedor{
    display: grid;
    grid-template-columns: 320px 320px 320px;
    align-items: center;
}
.contenedor_hijo{
    padding: 10px;
}

</style>