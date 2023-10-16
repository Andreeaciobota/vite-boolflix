<template>
  <div class="wrapper">

    <Header/>

    <Main :resultsArray="resultsArray"/>

  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'
export default {
  mounted(){
   this.getApi();
  },
  data(){
    return{
      resultsArray: [],
      apiURL: 'https://api.themoviedb.org/3/search/movie?api_key=9e5618652a0a8b25f8c8b66afcae4685&query=barbie',
    }
  },
  name: 'App',
  components: {
    Header,
    Main
  },
  methods:{
    getApi(){
      axios.get(this.apiURL)
      .then( r => {
        this.resultsArray = r.data.results;
        console.log(this.resultsArray);
      })
      .catch( e => {
        console.log(e);
      })
    },
  }
}
</script>

<style lang="scss">
 @import "src/style/generals.scss";
 @import "src/style/utilities.scss";
 @import "src/style/vars.scss";
</style>