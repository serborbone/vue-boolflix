<template>
  <ul>

    <li class="series" v-for="(series, index) in seriesData" :key="index">
        <!-- IMG SERIE -->
        <div class="movie-img">
          <img :src="'https://image.tmdb.org/t/p/w185' + series.poster_path">
        </div>
        
        <p> <span>Titolo:</span> {{series.name}} </p>
        <p> <span>Titolo originale:</span> {{series.original_name}} </p>
        <p> <span>Lingua originale:</span> <lang-flag :iso="series.original_language" /> </p>
        <p>
          <span>Voto:</span>
          <i v-for="i in 5" :key="i" class="fa-star" :class="(i < getVoteInt(index)) ? 'fa-solid' : 'fa-regular' "></i>
        </p>
    </li>

  </ul>
</template>

<script>
import LangFlag from '../../../node_modules/vue-lang-code-flags';

export default {
  name: 'cardSeries',

  components: {
    LangFlag,
  },

  props: ['seriesData'],

  methods: {
    getVoteInt(index) {
        return Math.ceil(this.seriesData[index].vote_average / 2);
      }
  },


}
</script>

<style lang="scss" scoped>
  @import '../style/main.scss';
</style>