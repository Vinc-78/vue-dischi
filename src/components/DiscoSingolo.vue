<template>

<div class="card" style="width: 18rem;">
  <img :src="poster" class="card-img-top" alt="...">

  <div class="card-body">
    <h5 class="card-title">{{title}}</h5>
    
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">{{author}}</li>
    <li class="list-group-item">{{genre}}</li>
    <li class="list-group-item">{{year}}</li>
  </ul>
 
</div>
    
</template>

<script>

export default {
    name: "DiscoSingolo",

    props:["poster","title","author","genre","year" ]
    

   
    
}
</script>
