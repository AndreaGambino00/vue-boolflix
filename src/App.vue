<template>
  <div id="app">
   <Header @performSearch="search" />
   <Main :movieCards="movies" />
   
  </div>
</template>

<script>
import Header from './components/Header.vue';
import axios from 'axios';
import Main from './components/Main.vue';



export default {
  name: 'App',
  components: {
    Header,
    Main,
 
  },
  data() {
    return {
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiKey: '9148d3b842c1e86c068b7ca934a94583',
      movies:[]
    }
  },

  methods: {
    getMovies(apiParams) {
       axios
       .get(this.apiUrl + 'movie', apiParams)
       .then( response => {
         this.movies = response.data.results;
       })
    },
    search(searchText) {
      const paramsObj = {
        params: {
          api_key: this.apiKey,
          query:searchText
        }
      };

      this.getMovies(paramsObj)
    }
  }
}
</script>

<style lang="scss">

</style>
