<template>
  <div class="my-main" >
   <MainComp/>

  </div>
</template>

<script>
import MainComp from './components/MainComp'


export default {
  name: 'App',
  components: {
    MainComp,
   
  }
}
</script>

<style lang="scss">
@import './assets/style/vars';
@import './assets/style/general';
@import './assets/style/mixin';

.my-main{
  background-color: $primary-color;
  min-height: 100vh;
}

</style>
