<template>
 <div class="text-centervmt-5 mb-4">
     <div class="input-group mx-auto" style="max-width:800px">
        <!-- Versione con il select -->
         <select
         class="form-control fs-3" 
         placeholder="Selexiona il genere di interesse..."

         v-model="genereRicercato"

        @keydown.enter="inizioRicerca">

        <option value="">All</option>
        <option value="rock">Rock</option>
        <option value="metal">Metal</option>
        <option value="pop">Pop</option>
        <option value="jazz">Jazz</option>

        </select>

        <button class="btn btn-outline-primary" type="button"

        @click="inizioRicerca"
        >Seleziona</button>

        <!-- Con il form di ricerca -->

         <!-- <input type="text" 
         class="form-control fs-3" 
         placeholder="Scrivi il genere di interesse..."

         v-model="genereRicercato"

         @keydown.enter="inizioRicerca">

        <button class="btn btn-outline-info fs-3" type="button"

        @click="inizioRicerca"
        >Seleziona</button> -->

     </div>

     <p class="mt-3 mb-4 text-white fs-3">Filtro attivo per il genere: 
         <strong class="mx-3 fs-2">{{genereRicercato}}</strong>
         <button class="btn-close btn-close-white btn-close-fs-1" @click="resetLista"></button></p>


 </div>

    
</template>

<script>

export default {
    name: "BarraDiRicerca",

    data(){
        return{
            genereRicercato:"",
        };
    },

    methods:{
        inizioRicerca(){
            this.$emit("startSearch",this.genereRicercato);
        },

        resetLista(){
          this.genereRicercato="" ;
          this.$emit("tuttaLaLista");
        }
    }

     
    
}
</script>
