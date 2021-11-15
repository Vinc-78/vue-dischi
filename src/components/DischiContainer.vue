<template>
<h1>prova</h1>
    
</template>

<script>
import axios from "axios";

export default {
    name: "DischiContainer",
    data() {
        return { elencoDischi: [], 
        };
    },

    mounted() {
        axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((risposta)=>{
            this.elencoDischi.push(...risposta.data);
        });
    }
    
}
</script>

<style lang="scss">

</style>