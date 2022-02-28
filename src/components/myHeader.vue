<template>
  <header id="header">

    <div class="logo">
        <h1>Boolflix</h1>
    </div>

    <div class="search">
      <input type="search" v-model="searchValue" v-on:keyup.enter="$emit('valueInput', searchValue)" placeholder="Cerca">
    </div>

  </header>
</template>

<script>
export default {
  name: 'myHeader',

  data() {
    return {

      searchValue: '',

    }
  },

}
</script>

<style lang="scss" scoped>

  @import '../assets/style/header.scss';

</style>