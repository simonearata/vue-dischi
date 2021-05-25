<template>
  
  <div class="container">

    <search 
      @searchAlbum="cercaAlbum"
    />

    <div class="row text-center">
      <Album 
        v-for="(album, index) in filterAlbums"
        :key="index"
        :album="album"
      />
    </div>
  </div>

</template>

<script>
import axios from 'axios'
import Album from '@/components/Album'
import Search from './Search.vue'


export default {
  name: 'MainComp',
  components:{
    Album,
    Search
  },
  data(){
    return{
      axios,
      albums:[],
      textSearch:''
    }
  },
  methods:{
    cercaAlbum(text){
      this.textSearch = text
    }
  },
  computed:{
    filterAlbums(){
      if(this.textSearch === ""){
        return this.albums
      }
      return this.albums.filter(item => item.genre === this.textSearch)
    }
  },
  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(res => {
      this.albums = res.data;
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