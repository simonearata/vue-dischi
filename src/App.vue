<template>
  <div id="app">
    <header-comp />

    <main-comp />

  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'



export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
    
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';
@import './assets/style/App/general.scss';

</style>
