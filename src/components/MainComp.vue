<template>
  
  <div v-if="!success" class="container">
    <div class="row text-center">
      <Album 
        v-for="(album, index) in albums.response"
        :key="index"
        :album="album"
      />
    </div>
  </div>
  <div v-else>Attendere...</div>

</template>

<script>
import axios from 'axios'
import Album from '@/components/Album'


export default {
  name: 'MainComp',
  components:{
    Album
  },
  data(){
    return{
      axios,
      albums:[],
      success: true
    }
  },

  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(res => {
      this.albums = res.data;
      this.success = false;
      console.log(res.data);
    })
    .catch(err => {
      console.log(err);
    })
  },
}
</script>

<style lang="scss" scoped>
@import '../assets/style/MainComp/style.scss'; 


</style>