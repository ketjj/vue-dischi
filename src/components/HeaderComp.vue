<template>
<div class="my-header">
  <div>
    <i class="fa-brands fa-spotify"></i>
  </div>
  
  <div class="input-group k_group">
    <select class="custom-select" id="inputGroupSelect04"
    v-model="chooseGenre"
    @change="$emit('selectGenre', chooseGenre)">
      <option value="">Seleziona un genere</option>
      <option value="Rock">Rock</option>
      <option value="Jazz">Jazz</option>
      <option value="Pop">Pop</option>
      <option value="Metal">Metal</option>
    </select>
  </div>


</div>
  
</template>

<script>
export default {
  name: 'HeaderComp',
  props:{
    albumItem:Object
  },
  data(){
    return{
      chooseGenre: ''
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/general';
@import '../assets/style/vars.scss';

.my-header{
  display:flex;
  justify-content: space-between;
  align-content: center;
  padding: 15px 20px;
  height: 65px;
  background-color: $secondary-color;
  i {
    color: #34be58;
    font-size: 2.5rem;
  }
  .k_group{
    width: 200px;
    #inputGroupSelect04{
      width:100%;
      border-radius: 5px;
      height: 35px;
    }
  }

}

</style>