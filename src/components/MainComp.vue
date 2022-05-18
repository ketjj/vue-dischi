<template>
<div>
  <HeaderComp 
  @selectGenre="selectRightGenre"/>
    <div class="k_container py-5">
      <div v-if="isLoad" class="album-container">
      <AlbumComps 
      v-for="(album,index) in filterGenres" :key="`album${index}`"
      :albumItem="album"
       />
       </div>
       <div v-else class="album-container2">
    <LoadComps /> 
    <!-- loadStatus="Loading... please wait!" -->
  </div>
</div>
</div>
  

</template>

<script>
import LoadComps from '@/components/LoadComps' 
import AlbumComps from '@/components/AlbumComps' 
import HeaderComp from '@/components/HeaderComp' 
// con ./ mi dava l'errore
import axios from 'axios';

export default {
  name: 'MainComp',
  components:{
    AlbumComps,
    LoadComps,
    HeaderComp
  },
  data(){
    return{
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      albums: [],
      isLoad: false,
      selectedGNR: '',
      //albumList: []
    }
  },
  mounted(){
    this.getApi()
  },

  methods:{
    getApi(){
      axios.get(this.apiUrl)
      .then(res =>{
        this.albums = res.data.response;
        this.isLoad = true;
        console.log(res.data.response.genre)
      })
    },
    selectRightGenre(chooseGenre){
      //console.log(chooseGenre, '------------')
      this.selectedGNR = chooseGenre;

    }
  },
  computed:{
    filterGenres(){
      let arrayFiltered = []
      if(this.selectedGNR == ''){
        arrayFiltered = this.albums
      }else {
        arrayFiltered = this.albums.filter((album) => album.genre == this.selectedGNR)
      }
      return arrayFiltered
    }
  }
}

  

</script>

<style lang="scss" scoped>
@import '../assets/style/general';
@import '../assets/style/vars';
.album-container{
  display: flex;
  flex-wrap: wrap;
}
.album-container2{
  text-align: center;
}

</style>