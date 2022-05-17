<template>
<div class="k_container">
  <AlbumComps />

</div>
  
</template>

<script>
import AlbumComps from '@/components/AlbumComps' 
// con ./ mi dava l'errore
import axios from 'axios';

export default {
  name: 'MainComp',
  components:{
    AlbumComps,
  },
  data(){
    return{
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      albums: []
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
      })
    }
  }

  }

</script>

<style lang="scss" scoped>
@import '../assets/style/general';

</style>