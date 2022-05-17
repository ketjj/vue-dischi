<template>
<div class="my-header">
  <div>
    <i class="fa-brands fa-spotify"></i>
  </div>
  
  <div class="input-group k_group">
    <select class="custom-select" id="inputGroupSelect04" aria-label="Example select with button addon">
      <option selected>Seleziona un genere</option>
      <option value="1">Rock</option>
      <option value="2">Jazz</option>
      <option value="3">Pop</option>
      <option value="4">Metal</option>
    </select>
  </div>

  

</div>
  
</template>

<script>
export default {
  name: 'HeaderComp'

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