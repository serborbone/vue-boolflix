<template>
  <main>
    <ul>
      <li v-for="(movie, index) in moviesList" :key="index">
        <p><span>Titolo:</span> {{movie.title}}</p>
        <p><span>Titolo originale:</span>  {{movie.original_title}}</p>
        <p><span>Lingua originale:</span>  {{movie.original_language}}</p>
        <p><span>Voto:</span>  {{movie.vote_average}}</p>
      </li>
    </ul>
  </main>
</template>

<script>
export default {
  name: 'myMain',
  props: ['moviesList'],
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/main.scss';
</style>