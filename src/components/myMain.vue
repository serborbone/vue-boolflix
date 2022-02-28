<template>
  <main>

    <!-- FILM -->
    <cardMovie :moviesData="moviesList"></cardMovie>
    
    <!-- SERIE TV -->
    <cardSeries :seriesData="tvSeries"></cardSeries>

  </main>
</template>

<script>

import cardMovie from '../assets/partials/cardMovie.vue';
import cardSeries from '../assets/partials/cardSeries.vue';

export default {
  name: 'myMain',
  components: {
    cardMovie,
    cardSeries,
  },
  props: ['moviesList', 'tvSeries'],
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/main.scss';
</style>