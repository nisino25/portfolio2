<template>
  <div class="home">
    <div class="introduction">
      <div class="balloon3-right" 
        data-aos="fade-right"
        data-aos-offset="0"
        data-aos-duration="2000"
        data-aos-delay="1500"
        deta-aos-once="false"
      >
        <span style="white-space: pre-wrap">
          <VueWriter :array="[`お客様の頭の中にあるアイディアを、\nヒアリングし実現する。\nそんなお手伝いができればと考えています。`]"
            :typeSpeed="50"
            :eraseSpeed="25"
            :delay="500"
            :interval="3500"
            :start="4000"
          />

          
        </span>

      </div>
      <img src="../../public/IMG_8167.png" alt="" 
        data-aos="fade-left"
        data-aos-offset="0"
        data-aos-duration="2000"
        data-aos-delay="1500"
        deta-aos-once="false"
        
      >


    </div>

    <div class="process">
      <h2 style="margin-bottom:150px">このような流れになります</h2>
      <div class="wrapper">


        <template v-for="(item,i) in process" :key="i">
          <div class="card-container"  
          data-aos="fade-up"
          data-aos-offset="200"
          data-aos-duration="750"
          data-aos-easing="ease-in-out"
          >
            <div class="process-card" :class="[i % 2 == 0 ? 'left' : 'right']" style="content: i">
              <div class="index">0{{i+1}}</div>
              <span>{{item.title}}</span><br>
              <span>{{item.description}}</span>
            </div>
            <div class="line-dot"></div>
          </div>

        
        </template>

      </div>
    </div>

    <div class="works" id="works">
      <h2>my works</h2>
      <img src="../../public/ScreenShot.png" alt="">
    </div>
    <div class="target" id="target">
      <h2>our targeted customres</h2>

      <div class="wrapper ">
        <template v-for="(item,i) in customers" :key="i">
          <div class="card" :style="getDelayAnimation(i)" 
            data-aos="flip-left"
            data-aos-offset="200"
            data-aos-duration="750">
            <img src="../../public/icons/professions/education-svgrepo-com.svg" class="" alt="">
            <br>
            <p>{{item.title}}</p> 

            <!-- <div class="img-wrapper">
              <img src="../../public/icons/professions/education-svgrepo-com.svg" class="" alt="">    
            </div>
            <div class="title-wrapper">
              <p>{{item.title}}</p>
            </div> -->
          </div>

          <!-- <div class="line-break" v-if="(i+1) % 3==0"></div> -->
        </template>

      </div>
    </div>



    <div class="skills">
      <div class="container">
        <h2 class="my-skills">My Skills</h2>
        <ul>
          <li v-for="(skill, i) in skillSet" :key="i">
            <div :style="{ width: skill.initLevel + '%'}">
              <label style="text-align: left">{{ skill.area }}</label>
              <!-- <label>{{ skill.initLevel + '%' }}</label> -->
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import {process} from '../const/process.js'
import {customers} from '../const/customers.js'


import VueWriter from "vue-writer";
import AOS from "aos";


export default {
  name: 'Home',
  components: {
    VueWriter,
    // AOS,
    // Slider,
    // SliderItem,
    // EasySlider,
    // HelloWorld

  },
  data(){
    return{
      process,
      customers,

      intervalID: '',
			increment: 1,
			skillSet: [
				{ area: 'java', initLevel: 0, level: 50 },
				{ area: 'c/c++', initLevel: 0, level: 60 },
				{ area: 'python', initLevel: 0, level: 70 },
				{ area: 'php', initLevel: 0, level: 80 },
				{ area: 'css3', initLevel: 0, level: 90 },
				{ area: 'html5', initLevel: 0, level: 100 }
			],


      vw: undefined
    }
  },
  mounted(){
    AOS.init()
    this.intervalID = setInterval(() => {
			this.getLevelProgress(this.increment)
		}, 10)

    document.getElementById('target').scrollIntoView();
  },

  methods:{
		getLevelProgress(value){
			this.skillSet.forEach(data => {
				data.initLevel = Math.min(Math.floor(data.initLevel+value), data.level)
			})
		},

    getDelayAnimation(i){
      return `transition-delay: ${0.6+ (i*0.18)}s`
      // if(i ==0){
      //   return `transition-delay: 0.6s`

      // }else if(i == 1 || i == 3){
      //   return `transition-delay: 0.8s`

      // }else if(i == 2 || i == 4 || i ==6){
      //   return `transition-delay: 1s`

      // }else if(i == 5 || i == 7){
      //   return `transition-delay: 1.2s`  
      // }else{
      //   return `transition-delay: 1.4s`  
      // }
    },

     



	},

  created(){
    console.clear()
    window.addEventListener('scroll', this.handleScroll);
    this.vw = document.documentElement.clientWidth 
    // console.log(this.vw)




    // this.incrementTotalViews()
  },
	// beforeDestroy: function() {
	// 	clearInterval(this.intervalID)
	// }
}

</script>

<style>
  .introduction{
    margin-top:-2em;
    background-color: #D6CDA4;
    /* display: block; */
    /* white-space: pre-wrap; */
    width: 100vw;
    left: 50%;
    transform: translateX(-50%);
    position: relative;
    /* display:flex; */
    /* position: relative; */
  }

  .balloon3-right {
    position: relative;
    display: inline-block;
    top: 50px;
    /* margin-top: 1.5em; */
    /* margin-right: 15em; */
    /* margin-left: -20em; */
    /* margin: 10em, 30em 0 40em; */
    padding: 2.5em 2.5em;
    width: 100%;
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

    /* opacity: 0; */
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
    position: absolute;
    font-size: 85%;
    width: 100%;
    /* background-color: red; */
    z-index:10;
  }

  .introduction img{
    height: 32.5em;
    width: auto;
    margin-top:1em;
    margin-left: 7.5em;
    margin-right: 0em
  }

/* process -------------------------------------------------------- */
.process{
  width: 100%;
  margin: 7.5em auto;


  
  /* background-position: top50px; */

  /* transform: translateY(20em);
  transition: all 1s ease; */
  /* opacity: 0; */

  /* transform: translateY(-100%); */

  /* temp */
  /* background-color: #D6CDA4; */
  /* display: flex;s */
  /* padding:0 0 0 0 ; */

  /* text-align: right; */

}

.process .wrapper{
  background-image: linear-gradient(#1C6758, #3D8361,#1C6758);
  background-size: 5px 90%;
  background-repeat: no-repeat;
  background-position: top 50px center ;

  position:relative;

  
  
  /* height: 90%; */
}

.card-container{
  position: relative;
}

.process-card{
  background-color: #3D8361;
  width: 40%;
  margin-top: 150px;
  /* margin: 0; */
  padding: 20px;
  color:#EEF2E6;
  border-radius: 5px;

  box-shadow: 0px 10px 20px #3D8361;
  padding: 25px;
}

.process-card .index{
  font-weight: bold;
  color: #D6CDA4;
  font-size: 120px;
  line-height: 100px;
  position: absolute;
  top: -95px;
  left: 0;
  right: 0;
  text-align: center;
  font-family: 'Montserrat', sans-serif;
  /* animation: stepscolor 3s infinite alternate; */


  opacity: 0.8
}

.process .left{
  position:relative;
  /* margin-left: 100px; */
  /* background-color: red; */
}

.process .right{
  position:relative;
  left:60%;
  /* float: right; */
  /* text-align:right; */
  /* margin-right: 0; */
  /* background-color: blue; */
}



.line-dot{
  z-index:10;

  aspect-ratio : 1 / 1;
  /* height:35%; */
  width: 2em;
  /* height: 30px; */

  border-radius: 50%;
  background-color: #EEF2E6; 
  position: absolute;
  border: 5px solid #3D8361;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  margin: auto;
}

/* works-------------------------------------------------------- */
.works{
  margin-top:15em;
}

.works img{
  width: 100%;
  height: auto;
}

/* target-------------------------------------------------------- */
.target{
  margin-top:15em;
  position:relative;

}

.target .wrapper{
  display: flex;
  width: 85%;
  flex-flow: row wrap;
  align-content: space-between;
  justify-content: space-between;

}

.target .wrapper .card {
  width: 15%;
  margin-top: 2em;
  padding: 0;
  /* color:red; */
  /* border-radius: 20px; */
  border-radius: 15px;
  overflow: hidden;
  perspective: 1px;
  /* border: 2px solid red;  */
    /* overflow: hidden; */

  background-color:  #D6CDA4;
  transition-timing-function: linear;
  transition: all 1.5s ease;
  
  transition-delay: 0s;
  
}

/* .target .card .img-wrapper{ 
  width: 100%;
  background-color: white;
  transition-timing-function: linear;
  transition: all 1.5s ease;
} */

.target .card:hover{ 
  background-color:     #3D8361;
  transition-delay: 0.1s;
  
}

.target .card img{
  height: auto;
  width: 3em;
  margin: 20px;
  /* padding:100px; */
}

.target .card .title-wrapper{
  background-color:  #D6CDA4;
  /* padding: 10px; */
  position:relative;
  width: 100%;
  padding: 2em;

  /* background-color: #aa21ff; */
  /* width: 100%; */
  /* padding: 15px; */
  /* display: flex; */
  /* justify-content: center; */
  /* align-items: center; */
  /* height: 6em; */
}

.target .card .title-wrapper p {
  /* margin: auto; */
  position: absolute;
  /* top: 0; left: 0; bottom: 0; right: 0; */
  top: 33%;
  left: 50%;
  transform: translateY(-50%);
  transform: translateX(-50%);
}

.line-break {
  width: 100%;
}






/* skills -------------------------------------------------------- */
.skills{
  margin-top:15em;
}





li {
	margin: .5em 0 .5em;
	border: .1em solid darken(rgb(109, 238, 133), 25%);
	border-radius: 3px;
	background: lighten(rgb(109, 238, 133), 25%);
	list-style: none;
	overflow: hidden;
}
li div {
  position: relative;
  height: 1.4em;
  background: rgb(109, 238, 133);
  font-size: 1.2em;
}
label:first-child {
  position: absolute;
  left: 8px;
}
li div label:last-child {
  position: absolute;
  right: 8px;
}
	

</style>