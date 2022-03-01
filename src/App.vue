<template>
  <div id="app">

    <myHeader @valueInput="getList"></myHeader>
    <myMain :moviesList="movies" :tvSeries="tvSeries"></myMain>

  </div>
</template>

<script>

import myHeader from './components/myHeader.vue'
import myMain from './components/myMain.vue'

export default {
  name: 'App',


  components: {
    myHeader,
    myMain,
  },

  data() {

    return {
      api_key: '388fabb7ed8aede6b92c0e07105b000e',
      language: 'it-IT',

      movies: [],
      tvSeries: [],
    }

  },

  methods: {

      getList(keyword) {
      
        const axios = require('axios');

        let movieRequest = 'https://api.themoviedb.org/3/search/movie?api_key='+ this.api_key + '&query=" ' + keyword + '"&language=' + this.language + ' ';
        let tvRequest = 'https://api.themoviedb.org/3/search/tv?api_key='+ this.api_key + '&query=" ' + keyword + '"&language=' + this.language + ' ';
        
        //richiesta axios per FILM
        axios.get(movieRequest)
        .then((movieRequest) => {

          this.movies = movieRequest.data.results;
          console.log(this.movies)
          
        })

        //richiesta axios per SERIE TV
        axios.get(tvRequest)
        .then((tvRequest) => {

          this.tvSeries = tvRequest.data.results;

        })
        .catch(function (error) {
          console.log(error);
        })
        .then(function () {
        });

      }

  },

}
</script>

<style lang="scss">
  @import './assets/style/general.scss';
</style>
