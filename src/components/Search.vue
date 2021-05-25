<template>
  <form class="d-flex justify-content-center">
    <div class="box_input">
      <input 
        class="form-control"
        type="text"
        placeholder="Cerca Genere"
        v-model="searchText"
        @keyup.enter="albumSearch"
      >
    </div>
    <div class="box_btn">
      <button 
        class="btn"
        @click.prevent="albumSearch"
      >Cerca</button>
      <button class="btn">Reset</button>
    </div>
  </form>
</template>

<script>
export default {
  name: 'Search',
  data(){
    return{
      searchText: ''
    }
  },
  methods:{
    albumSearch(){
      this.$emit('searchAlbum', this.searchText);
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/MainComp/search_style.scss'; 

</style>