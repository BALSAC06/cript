<template>
    
   <body>
    <H2>LUGARES</H2>
        <div class="box">
            <section  style="margin: 0 auto; padding-bottom: 1rem; padding-top:1rem ; display: block; text-align: center; margin: 1rem; color :black; border: solid gold 4px;" v-for="value in character" >
            
            <div class="content">
                
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
    </body>
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
body{
    background-image: url(../c137.webp)
    ;
    align-content: center;
    align-items: center;
}

.box{
    display: grid;
    grid-template-columns: 360px 360px 360px 360px;
    align-items: center;
    margin: 0 auto;
    border-radius: 5rem;
}
.content{
    padding: 10px;
    margin: 0 auto;
}
h2{
    background-color: gold;
    font-size: 5rem;
    font-family: cursive;
}

</style>