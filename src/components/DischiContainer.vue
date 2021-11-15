<template>

<div class="container-fluid bg-dark">

<div class="nav" ></div>

<div class="container py-5">
  <div class="row row-cols-5 g-4 pt-5">

      <div class="col " v-for="(disco,i) in elencoDischi" :key="i">
          
          <DiscoSingolo 
          :poster="disco.poster"
          :title="disco.title"
          :author="disco.author"
          :genre="disco.genre"
          :year="disco.year"
          >
          </DiscoSingolo>


      </div>


  </div>

</div>
    

</div>

    
</template>

<script>
import axios from "axios";
import DiscoSingolo from "./DiscoSingolo.vue"


export default {
    name: "DischiContainer",

    components: {
        DiscoSingolo,
        

    },

    data() {
        return { elencoDischi: [], 
        };
    },

    mounted() {
        axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((risposta)=>{
            
            this.elencoDischi.push(...risposta.data.response);
        });
    }
    
}
</script>

<style lang="scss">

</style>