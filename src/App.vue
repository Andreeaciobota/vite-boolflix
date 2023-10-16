<template>
  <div class="wrapper">

    <Header @sendQuerySearch="querySearchFunction"/>

    <Main :arrayConcat="arrayConcat" />

  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'
export default {
 //mounted(){
 // this.getApi();
//},
  data(){
    return{
      resultsArray: [],
      resultsArrayTv: [],

      arrayConcat: [],

      apiKey: 'api_key=9e5618652a0a8b25f8c8b66afcae4685&',
      filmserie: 'Film',
      querySearch: '',
      language: '&language=it_IT',
      page: '&page=1',

      apiURLmovie:'https://api.themoviedb.org/3/search/movie?',
      apiURLtv:'https://api.themoviedb.org/3/search/tv?',
    }
  },
  name: 'App',
  components: {
    Header,
    Main
  },
  methods:{
    getApiMovie(){
      axios.get(`${this.apiURLmovie}${this.apiKey}'&query='${this.querySearch}`)
      .then( r => {
        this.resultsArray = r.data.results;
      })
      .catch( e => {
        console.log(e);
      })
    },
    getApiTv(){
      axios.get(`${this.apiURLtv}${this.apiKey}'&query='${this.querySearch}`)
      .then( resp => {
        this.resultsArrayTv = resp.data.results;
        this.arrayConcat = this.resultsArray.concat(this.resultsArrayTv);
        // console.log('search query',this.querySearch);
        // console.log('array film',this.resultsArray);
        // console.log('array tv',this.resultsArrayTv);
        // console.log('array concatenato', this.arrayConcat);
      })
      .catch( e => {
        console.log(e);
      })
    },
    // concatFunction(){
    //   if(this.resultsArray.length > 0 || this.resultsArrayTv.length > 0 ){
    //     this.arrayConcat = [...this.resultsArray, ...this.resultsArrayTv]
    //   }else if(this.resultsArray.length > 0 || this.resultsArrayTv.length < 1 ){
    //     this.arrayConcat = this.resultsArray;
    //   }else if(this.resultsArray.length < 1 || this.resultsArrayTv.length > 0 ){
    //     this.arrayConcat = this.resultsArrayTv;
    //   }else{
    //     this.arrayConcat;
    //   }
    //   return this.arrayConcat  
    // },
    querySearchFunction(text){
      this.querySearch = text;
       this.getApiMovie();
       this.getApiTv();
      
        console.log('search query',this.querySearch);
        console.log('array film',this.resultsArray);
        console.log('array tv',this.resultsArrayTv);
        console.log('array concatenato', this.arrayConcat);
      
    }
  }
}
</script>

<style lang="scss">
 @import "src/style/generals.scss";
 @import "src/style/utilities.scss";
 @import "src/style/vars.scss";
</style>