<template>
  <div id="app">
  
  <main><DischiContainer></DischiContainer></main>
   


  </div>
</template>

<script>
import DischiContainer from "./components/DischiContainer.vue"


export default {
  name: 'App',
  components: {
    DischiContainer
  }
}
</script>

<style lang="scss">
@import "@/styles/generale.scss";

</style>
