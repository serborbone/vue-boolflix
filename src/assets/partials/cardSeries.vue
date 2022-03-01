<template>
  <ul>

    <li class="card" v-for="(series, index) in seriesData" :key="index">
        <div class="card-inner">
          <!-- IMG SERIE -->
          <div class="card-front">
            <img v-if="series.poster_path" :src="'https://image.tmdb.org/t/p/w342' + series.poster_path">
            <img v-else class="else-img" src="../style/img/img-else.jpg">
          </div>
          
          <div class="card-back">
            <div class="info-wrap">

              <p> <span>Titolo:</span> {{series.name}} </p>
              <p> <span>Titolo originale:</span> {{series.original_name}} </p>
              <p> <span>Lingua originale:</span> <lang-flag :iso="series.original_language" /> </p>
              <p>
                <span>Voto:</span>
                <i v-for="i in 5" :key="i" class="star-color fa-star" :class="(i < getVoteInt(index)) ? 'fa-solid' : 'fa-regular' "></i>
              </p>

              <p :class="series.overview? '' : 'd-none' ">
                <span>Trama:</span> 
                {{series.overview}}
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
  @import '../style/cardstyle.scss';
</style>