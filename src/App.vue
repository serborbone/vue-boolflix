<template>
  <div id="app">

    <myHeader></myHeader>

  </div>
</template>

<script>

import myHeader from './components/myHeader.vue'

export default {
  name: 'App',
  components: {
    myHeader,
  }
}
</script>

<style lang="scss">
  @import './assets/style/general.scss';
</style>
