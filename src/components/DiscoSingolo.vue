<template>

<div class="card " >
  <img :src="poster" class="card-img-top " alt="...">

  <div class="card-body">
    <h5 class="card-title text-center fs-4">{{title}}</h5>
    
  </div>
  <div class="card-text text-center fs-5">
        <ul>
          <li> {{ author }}</li>
          <li> {{ genre }}</li>
          <li> {{ year }}</li>
        </ul>
    </div>
  
</div>
    
</template>

<script>

export default {
    name: "DiscoSingolo",

    props:["poster","title","author","genre","year" ]
    

   
    
}
</script>
