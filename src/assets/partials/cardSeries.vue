<template>
  <ul>

    <li class="series" v-for="(series, index) in seriesData" :key="index">
        <p> <span>Titolo:</span> {{series.name}} </p>
        <p> <span>Titolo originale:</span> {{series.original_name}} </p>
        <p> <span>Lingua originale:</span> <lang-flag :iso="series.original_language" /> </p>
        <p> <span>Voto:</span> {{series.vote_average}} </p>
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
}
</script>

<style lang="scss" scoped>
  @import '../style/main.scss';
</style>