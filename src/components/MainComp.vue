<template>
<div class="k_container py-5">
  <div v-if="isLoad" class="album-container">
    <AlbumComps 
    v-for="(album,index) in albums" :key="`album${index}`"
    :albumItem="album"
    />
  </div>
  <div v-else class="album-container2">
    <LoadComps /> 
    <!-- loadStatus="Loading... please wait!" -->
  </div>

</div>
  
</template>

<script>
import LoadComps from '@/components/LoadComps' 
import AlbumComps from '@/components/AlbumComps' 
// con ./ mi dava l'errore
import axios from 'axios';

export default {
  name: 'MainComp',
  components:{
    AlbumComps,
    LoadComps
  },
  data(){
    return{
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      albums: [],
      isLoad: false
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
      })
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