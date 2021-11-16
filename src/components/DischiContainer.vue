<template>
  <div class="container-fluid bg-dark">
    <div class="nav"></div>

    <div class="container py-5">
      <BarraDiRicerca 
      @startSearch="filtroDischi"
      @tuttaLaLista="ripristinaLista">
      
      </BarraDiRicerca>

      <div class="row row-cols-5 g-4 pt-3">
        <div class="col" v-for="(disco, i) in generaListaFiltrata" :key="i">
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
import DiscoSingolo from "./DiscoSingolo.vue";
import BarraDiRicerca from "./BarraDiRicerca.vue";

export default {
  name: "DischiContainer",

  components: {
    DiscoSingolo,
    BarraDiRicerca,
  },

  data() {
    return {
      elencoDischi: [],
      genereCercato: "",
    };
  },

  methods: {
    filtroDischi(genere) {
      this.genereCercato = genere;

      console.log("ora genereCercato è " + this.genereCercato);
    },

    ripristinaLista() {
        this.genereCercato ="";
    }
  },

  computed: {
    generaListaFiltrata() {
      if (!this.genereCercato) {
        return this.elencoDischi;
      }


      return this.elencoDischi.filter(elemento => {
        return elemento.genre.toLowerCase().includes(this.genereCercato.toLowerCase().trim())
      });

    

      
    },
  },

  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((risposta) => {
        this.elencoDischi.push(...risposta.data.response);
      });
  },
};
</script>