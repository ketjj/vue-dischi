<template>
<div>
  <!-- {{loadStatus}} -->
  <div class="loader2"></div>
  <div class="loader"></div>
</div>
  
</template>

<script>
export default {
  name: 'LoadComps',
  props: {
    // loadStatus:String
  }

}
</script>

<style lang="scss" scoped>
div{
  font-size: 20px;
  color: white;
  .loader {
      width: 100px;
      height: 100px;
      margin: 0 auto;
      margin-top: 20px;
      position: relative;
      background: #FFF;
      border-radius: 4px;
      overflow: hidden;
    }
    .loader:before {
      content: "";
      position: absolute;
      left: 0;
      bottom: 0;
      width: 100px;
      height: 100px;
      transform: rotate(45deg) translate(30%, 40%);
      background: #ff9371;
      box-shadow: 32px -34px 0 5px #ff3d00;
      animation: slide 2s infinite ease-in-out alternate;
    }
    .loader:after {
      content: "";
      position: absolute;
      left: 10px;
      top: 10px;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      background: #ff3d00;
      transform: rotate(0deg);
      transform-origin: 35px 145px;
      animation: rotate 2s infinite ease-in-out;
    }

    @keyframes slide {
      0% , 100%{ bottom: -35px}
      25% , 75%{ bottom: -2px}
      20% , 80%{ bottom: 2px}
    }
    @keyframes rotate {
      0% { transform: rotate(-15deg)}
      25% , 75%{ transform: rotate(0deg)}
      100% {  transform: rotate(25deg)}
    }

    .loader2{
      font-size: 48px;
      color: #FFF;
      display: inline-block;
      font-family: Arial, Helvetica, sans-serif;
      font-weight: 400;
      position: relative;
    }
    .loader2:before{
      content: '';
      animation: 5s print linear alternate infinite;
    }
    .loader2:after{
      content: '';
      position: absolute;
      right: -4px;
      top: 50%;
      transform: translatey(-45%);
      width: 2px;
      height: 1.3em;
      background: currentColor;
      opacity: 0.8;
      animation: 1s blink steps(2) infinite;
    }
    
    @keyframes blink {
      0%  { visibility: hidden;}
      100%  { visibility: visible;}
    }
    @keyframes print {
      0% { content: 'L'}
      10% { content: 'Lo'}
      20% { content: 'Loa'}
      30% { content: 'Load'}
      40% { content: 'Loadi'}
      50% { content: 'Loadin'}
      60% { content: 'Loading'}
      70% { content: 'Loading.'}
      80% { content: 'Loading..'}
      90% , 100% { content: 'Loading...'}
    }
  
}

</style>