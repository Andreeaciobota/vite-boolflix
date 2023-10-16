<template>
  <header class="fc-flex fc-between fc-align-center">
    <div class="logo"></div>

    <div class="search-bar fc-flex fc-between fc-align-center">
      <input v-model="search" placeholder="cerca un film">
      <button>click</button>   
    </div>  
  </header>
</template>

<script>
export default {
  name: 'Header',
  data(){
    return{
      search: ''
    }
  }
}
</script>

<style lang="scss">
 header{
   height: 100px;
   background-color: black;
   color: white;
    .logo{
      width: 200px;
      background-color: rgb(142, 10, 30);
      height: 80px;
    }
    .search-bar{
      width: 300px;
      background-color: rgb(198, 105, 186);
      height: 80px;
      padding: 10px;
        input{
         width: 65%;
         height: 25px;
         border: none;
         padding-left: 5px;
        }
        button{
          width: 30%;
          height: 25px;
          border-radius: 0;
          border: none;
          cursor: pointer;
        }
    }
 }
</style>