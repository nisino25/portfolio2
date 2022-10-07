<template>
  <div class="home">
    <div class="introduction">
      <div class="balloon3-right" id="slide">
        sup
      </div>
      <img src="../../public/kisspng-clip-art-vector-graphics-silhouette-openclipart-fr-5d28e041717207.0618147015629599374647.png" alt="">


    </div>

    
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld
  }
}
</script>


<style>
  .introduction{
    background-color: #D6CDA4;
  }

  .balloon3-right {
    position: relative;
    display: inline-block;
    margin: 1.5em 15px 1.5em 0;
    padding: 0 5px;
    width: 90px;
    height: 90px;
    line-height: 90px;
    text-align: center;
    color: #FFF;
    font-size: 20px;
    font-weight: bold;
    background: #ff8e9d;
    border-radius: 50%;
    box-sizing: border-box;
  }

  .balloon3-right:before {
    content: "";
    position: absolute;
    top: 50%;
    right: -25px;
    margin-top: -15px;
    border: 15px solid transparent;
    border-left: 15px solid #ff8e9d;
    z-index: 0;
  }


  #slide {
    animation: slide 1s forwards;
    animation-delay: 2s;
      /* position: absolute;
      left: -100px;
      width: 100px;
      height: 100px;
      background: blue;
      -webkit-animation: slide 0.5s forwards;
      -webkit-animation-delay: 2s;
      animation: slide 0.5s forwards;
      animation-delay: 2s; */
  }

    @keyframes slide {
    0% {
    transform: translateX(0px);
    }

    100% {
    transform: translateX(300px);
    }
  }





  .introduction img{
    height: 350px;
    width: auto;
    padding-top: 50px;
    margin-left: 450px;
  }
</style>