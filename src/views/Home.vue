<template>
  <div class="home">
    <div class="introduction">
      <div class="balloon3-right" id="slide">
        <span>
          <VueWriter :array="[`お客様の頭の中にあるアイディアを、
ヒアリングし実現する。
そんなお手伝いができればと考えています。`]"
            :typeSpeed="50"
            :eraseSpeed="25"
            :delay="3000"
            :interval="3000"
            :start="3500"
          />

          
        </span>
      </div>
      <img src="../../public/kisspng-clip-art-vector-graphics-silhouette-openclipart-fr-5d28e041717207.0618147015629599374647.png" alt="">


    </div>

    
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
import VueWriter from "vue-writer";
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    VueWriter,
    // HelloWorld

  }
}
</script>


<style>
  .introduction{
    background-color: #D6CDA4;
    display: block;
    white-space: pre-wrap;
    /* position: relative; */
  }

  .balloon3-right {
    /* position: relative; */
    display: inline-block;
    margin-top: 2em;
    margin-right: 15em;
    margin-left: -20em;
    /* margin: 10em, 30em 0 40em; */
    padding: 2.5em 2.5em;
    width: 90px;
    height: 12.5em;
    width: 20em;
    line-height: 50px;
    color: #FFF;
    font-size: 1.5em;
    font-weight: bold;
    background: #3D8361;
    border-radius: 50%;
    box-sizing: border-box;
    text-align: left;
    overflow:hidden;
    /* display: none */
  }

  .balloon3-right:before {
    content: "";
    position: absolute;
    top: 50%;
    right: -25px;
    margin-top: -15px;
    border: 15px solid transparent;
    border-left: 15px solid #3D8361;
    z-index: 0;
  }

  .balloon3-right span{
    font-size: 85%;
  }


  #slide {
    animation: slide 1s forwards;
    animation-delay: 2.5s;
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
    transform: translateX(17.5em);
    }
  }





  .introduction img{
    height: 350px;
    width: auto;
    padding-top: 50px;
    margin-left: 5em;
    /* position: absolute; */
  }
</style>