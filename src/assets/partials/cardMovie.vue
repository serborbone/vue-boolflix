<template>
  <ul>

    <li v-for="(movies, index) in moviesData" :key="index">
        <!-- IMG FILM -->
        <div class="movie-img">
          <img :src="'https://image.tmdb.org/t/p/w185' + movies.poster_path">
        </div>
        
        <p><span>Titolo:</span> {{movies.title}}</p>
        <p><span>Titolo originale:</span>  {{movies.original_title}}</p>
        <p><span>Lingua originale:</span> <lang-flag :iso="movies.original_language" /> </p>
        <p><span>Voto:</span>  {{movies.vote_average}}</p>
    </li>

  </ul>
</template>

<script>
import LangFlag from '../../../node_modules/vue-lang-code-flags';

export default {
  name: 'cardMovie',

  components: {
    LangFlag,
  },

  props: ['moviesData'],
}
</script>

<style lang="scss" scoped>
  @import '../style/main.scss';
</style>