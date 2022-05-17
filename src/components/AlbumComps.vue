<template>
  <div class="k_card">
    <img :src="albumItem.poster" :alt="albumItem.title">
    <div class="title-card">{{albumItem.title}}</div>

    <div class="singer-year">
      <div>{{albumItem.author}}</div>
      <div>{{albumItem.year}}</div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'AlbumComps',
  props:{
    albumItem:Object
  }

}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';
@import '../assets/style/mixin.scss';

.k_card{
  width: 185px;
  min-height: 200px;
  padding: 15px;
  margin: 0 .8rem 2rem .8rem;
  background-color: $secondary-color;
  text-align: center;
  color:white;
  img{
    width:100%;
    margin-bottom: 6px;
  }
  .title-card{
    @include upper;
    margin-top: 8px;
    font-size: 14px;
  }
  .singer-year{
    font-size: 14px;
    color: grey;
    margin-top:15px;
    font-weight: 500;
  }
}

</style>