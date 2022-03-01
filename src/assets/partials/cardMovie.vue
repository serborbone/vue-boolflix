<template>
  <ul>

    <li class="card" v-for="(movies, index) in moviesData" :key="index">
        <div class="card-inner">
          <!-- IMG FILM -->
          <div class="card-front">
            <img v-if="movies.poster_path" :src="'https://image.tmdb.org/t/p/w342' + movies.poster_path">
            <img v-else class="else-img" src="../style/img/img-else.jpg">
          </div>
          
          <div class="card-back">
            <div class="info-wrap">
              <p><span>Titolo:</span> {{movies.title}}</p>
              <p><span>Titolo originale:</span>  {{movies.original_title}}</p>
              <p><span>Lingua originale:</span> <lang-flag :iso="movies.original_language" /> </p>
              <p>
                <span>Voto:</span>
                <i v-for="i in 5" :key="i" class="star-color fa-star" :class="(i < getVoteInt(index)) ? 'fa-solid' : 'fa-regular' "></i>
              </p>

              <p :class="movies.overview? '' : 'd-none' ">
                <span>Trama:</span> 
                {{movies.overview}}
              </p>
              
            </div>
          </div>

        </div>
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

  methods: {

    getVoteInt(index) {
      return Math.ceil(this.moviesData[index].vote_average / 2);
    }

  },

}
</script>

<style lang="scss" scoped>
  @import '../style/cardstyle.scss';
</style>