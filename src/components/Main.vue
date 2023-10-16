<template>
  <main class="fc-container fc-flex fc-wrap">
    <div v-for="item in arrayConcat" :key="item.id" class="card">

<h2 v-if="item.hasOwnProperty('title')"> {{item.title}} </h2>
<h2 v-if="item.hasOwnProperty('name')"> {{item.name}} </h2>

 <ul>
   <li v-if="item.hasOwnProperty('original_title')"> Titolo originale: {{item.original_title}} </li>
   <li v-if="item.hasOwnProperty('original_name')"> Titolo originale: {{item.original_name}} </li>
   <li> Lingua: {{item.original_language}} </li>
   <li> Voto: {{item.vote_average}} </li>   
   <li> Trama: {{item.overview}} </li>   
 </ul>
      <h2> {{item.title}} </h2>
       <ul>
         <li> Titolo originale: {{item.original_title}} </li>
         <li> Lingua: {{item.original_language}} </li>
         <li> Voto: {{item.vote_average}} </li>   
       </ul>
    </div>
  </main>
</template>

<script>
export default {
  name: 'Main',
  props:{
     arrayConcat: Array
  },
  isMovie: false,
}
</script>

<style lang="scss">

 main{
  min-height: calc(100vh - 100px);
  background-color: rgb(170, 9, 44);
   .card{
     height: 400px;
     width: 230px;
     background-color: rgb(232, 114, 167);
     border: 1px solid white;
     padding: 10px;
     margin: 5px;
     overflow: hidden;
       h2{
         margin-bottom: 40px;
       }
       li{
         margin-bottom: 20px;
       }
   }
 }
</style>