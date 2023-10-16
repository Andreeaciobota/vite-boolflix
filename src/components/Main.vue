<template>
  <main class="fc-container fc-flex fc-wrap">
    <div v-for="item in resultsArray" :key="item.id" class="card">
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
     resultsArray: Array
  }
}
</script>

<style lang="scss">
 main{
  height: calc(100vh - 100px);
  background-color: rgb(170, 9, 44);
   .card{
     height: 400px;
     width: 230px;
     background-color: rgb(232, 114, 167);
     border: 1px solid white;
     padding: 10px;
     margin: 5px;
       h2{
         margin-bottom: 40px;
       }
       li{
         margin-bottom: 20px;
       }
   }
 }
</style>