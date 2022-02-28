<template>
  <div id="app">

    <myHeader @valueInput="getList"></myHeader>
    <myMain :moviesList="movies"></myMain>

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
    }

  },

  methods: {

      getList(keyword) {
      
        const axios = require('axios');
        axios.get('https://api.themoviedb.org/3/search/movie?api_key='+ this.api_key + '&query=" ' + keyword + '"&language=' + this.language + ' ')
        .then((response) => {

          //console.log(response);

          this.movies = response.data.results;

          console.log(this.movies);


        })
        .catch(function (error) {
          console.log(error);
        })
        .then(function () {
        });

      }

  },

  mounted() {

    this.getList();

  },
}
</script>

<style lang="scss">
  @import './assets/style/general.scss';
</style>
