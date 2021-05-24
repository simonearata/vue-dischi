<template>
  <div  
    class="col-2 col-half-offset box_album"
  >
    <div class="box_img">
      <img :src="album.poster" alt="">
    </div>
    <h3>{{ album.title }}</h3>
    <p>{{ album.author }}</p>
    <p>{{ album.year }}</p>
  </div>
</template>

<script>
export default {
  name: 'Album',
  props:{
    album: Object
  }
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/Album/style.scss'; 
</style>