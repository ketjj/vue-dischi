<template>
  <div class="my-main" >

   <HeaderComp />
   <MainComp/>

  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp'
import MainComp from './components/MainComp'


export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
   
  }
}
</script>

<style lang="scss">
@import './assets/style/vars';
@import './assets/style/general';
@import './assets/style/utilities';
@import './assets/style/mixin';

.my-main{
  background-color: $primary-color;
  height: 100vh;
}

</style>
