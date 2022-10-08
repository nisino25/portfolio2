<template>
  <div class="loading"  :class="[showingLoading? '' : 'fadeOut']">
    <img src="../public/loading.gif" alt="" >
  </div>
  <div>

    <header>
      <div class="top-nav">
        <h1 id="logo" ><a href="/">Nozomu Ando</a></h1>
        <div class="socialBtn">
          <a href="http://instagram.com/nisino25" target="_blank">
            <img src="../public/icons/ig-icon.png" alt="">
          </a>
  
          <a href="#" target="_blank">
            <img src="../public/icons/twitter-icon.png" alt="">
          </a>
        </div>
  
      </div>
      <nav>
        <ul class="">
          <li class="about"><a href="/about">About</a></li>
          <li class="works"><a href="/works">Works</a></li>
          <li class="blog"><a href="/blog">Blog</a></li>
          <li class="contact"><a href="/contact">Contact</a></li>
        </ul>
      </nav>
      
      
    </header>
  
  
    <router-view/>
    <!-- <h1 class="text-danger">hey</h1> -->
  
    <footer class="footer-section">
      <div class="container">
        <div class="footer-cta pt-2 pb-2">
  
          <div class="row">
  
            <div class="col-xl-6 col-md-6 mb-30">
              <div class="single-cta">
                <i class="fas fa-phone"></i>
                <div class="cta-text">
                  <h4 class="danger">Call us</h4>
                  <span>9876543210 0</span>
                </div>
              </div>
            </div>
  
            <div class="col-xl-6 col-md-6 mb-30">
              <div class="single-cta">
                <i class="far fa-envelope-open"></i>
                <div class="cta-text">
                  <h4>Mail us</h4>
                  <span>mail@info.com</span>
                </div>
              </div>
            </div>
            
          </div>
        </div>
  
        <div class="footer-content pt-5 pb-5">
            <div class="row">
                <div class="col-xl-4 col-lg-4 mb-50">
                    <div class="footer-widget">
                        <div class="footer-logo">
                            <a href="index.html"><img src="https://i.ibb.co/QDy827D/ak-logo.png" class="img-fluid" alt="logo"></a>
                        </div>
                        <div class="footer-text">
                            <p>Lorem ipsum dolor sit amet, consec tetur adipisicing elit, sed do eiusmod tempor incididuntut consec tetur adipisicing
                            elit,Lorem ipsum dolor sit amet.</p>
                        </div>
                        <div class="footer-social-icon">
                            <span>Follow us</span>
                            <a href="#"><i class="fab fa-facebook-f facebook-bg"></i></a>
                            <a href="#"><i class="fab fa-twitter twitter-bg"></i></a>
                            <a href="#"><i class="fab fa-google-plus-g google-bg"></i></a>
                        </div>
                    </div>
                </div>
                <div class="col-xl-4 col-lg-4 col-md-6 mb-30">
                    <div class="footer-widget">
                        <div class="footer-widget-heading">
                            <h3>Useful Links</h3>
                        </div>
                        <ul>
                            <li><a href="#">Home</a></li>
                            <li><a href="#">about</a></li>
                            <li><a href="#">services</a></li>
                            <li><a href="#">portfolio</a></li>
                            <li><a href="#">Contact</a></li>
                            <li><a href="#">About us</a></li>
                            <li><a href="#">Our Services</a></li>
                            <li><a href="#">Expert Team</a></li>
                            <li><a href="#">Contact us</a></li>
                            <li><a href="#">Latest News</a></li>
                        </ul>
                    </div>
                </div>
                <div class="col-xl-4 col-lg-4 col-md-6 mb-50">
                    <div class="footer-widget">
                        <div class="footer-widget-heading">
                            <h3>Subscribe</h3>
                        </div>
                        <div class="footer-text mb-25">
                            <p>Don’t miss to subscribe to our new feeds, kindly fill the form below.</p>
                        </div>
                        <div class="subscribe-form">
                            <form action="#">
                                <input type="text" placeholder="Email Address">
                                <button><i class="fab fa-telegram-plane"></i></button>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
      </div>
      <div class="copyright-area">
          <div class="container">
              <div class="row">
                  <div class="col-xl-6 col-lg-6 text-center text-lg-left">
                      <div class="copyright-text">
                          <p>Copyright &copy; 2018, All Right Reserved <a href="https://codepen.io/anupkumar92/">Anup</a></p>
                      </div>
                  </div>
                  <div class="col-xl-6 col-lg-6 d-none d-lg-block text-right">
                      <div class="footer-menu">
                          <ul>
                              <li><a href="#">Home</a></li>
                              <li><a href="#">Terms</a></li>
                              <li><a href="#">Privacy</a></li>
                              <li><a href="#">Policy</a></li>
                              <li><a href="#">Contact</a></li>
                          </ul>
                      </div>
                  </div>
              </div>
          </div>
      </div>
    </footer>
  </div>

</template>

<script>
  export default{
    data(){
      return{
        showingLoading: true,
      }
    },

    methods:{
      test(){
        console.log('hey')

      },
      sleep(ms) {
        return new Promise((resolve) => {
          setTimeout(resolve, ms);
        });
      },


      async startUp(){
        await this.sleep(1000)
        this.showingLoading = false

      },
    },

    mounted(){
      this.startUp()
    }
    
  }
</script>

<style>
  .loading{
    position: absolute;
    top:0;
    left: 0;
    width: 100vw;
    height: 100vh;
    
    /* color: #fff; */
    z-index: 100;
    text-align: center;
    background-color: white;


    opacity: 1;
    transition: opacity .5s ease-in-out;
    -moz-transition: opacity .5s ease-in-out;
    -webkit-transition: opacity .5s ease-in-out;
   

  }

  .loading img{
    position: absolute;
    top: 50%; 
    left: 50%;

    width: 150px;
    height: auto;

    margin-top: -75px;  
    margin-left: -75px;

  }

  .fadeOut {
      opacity:0;
  }

/* 
#1C6758
#
#
#
*/

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #EEF2E6;
  /* color: #2c3e50; */
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  
}

header{
  padding: 100px;
  width: 90%;
  max-width: 1000px;
  margin: auto auto;
  list-style: none;
}

.top-nav{
  /* background-color: red; */
  /* display: inline; */
  display: flex;
  position: relative;

}

header h1{
  margin: 0;
  text-align: left;
}

.socialBtn{
  position: absolute;
  right: 0;
  /* right: 0; */
  /* text-align: right; */
}

header div{
  text-align: right;
}

header img{
  width: 35px;
  height: auto;
  margin-left: 17.5px
  
}

nav ul{
  margin-top: 75px;
  text-align: right;
  
}

a, a:hover{
  color: black;
}

nav ul li{
  
  list-style: none;
  display: inline;
  margin-left: 20px;
  font-size: 125%;
  /* color: inherit; */
  text-decoration: none;
  /* display: flex; */
}

/* *  For Mobile Screens  */ 

@media screen and (max-width: 700px) {
  
}

/* -------------------------------------------------------------- */
ul {
  margin: 0px;
  padding: 0px;
}
.footer-section {
  background: #3D8361;
  position: relative;
  margin-top: 100px;
}
.footer-cta {
  border-bottom: 1px solid #373636;
}
.single-cta i {
  color: #ff5e14;
  font-size: 30px;
  float: left;
  margin-top: 8px;
}
.cta-text {
  padding-left: 15px;
  display: inline-block;
}
.cta-text h4 {
  color: #fff;
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 2px;
}
.cta-text span {
  /* color: #757575; */
  /* color: red; */
  font-size: 15px;
}
.footer-content {
  position: relative;
  z-index: 2;
}
.footer-pattern img {
  position: absolute;
  top: 0;
  left: 0;
  height: 330px;
  background-size: cover;
  background-position: 100% 100%;
}
.footer-logo {
  margin-bottom: 30px;
}
.footer-logo img {
    max-width: 200px;
}
.footer-text p {
  margin-bottom: 14px;
  font-size: 14px;
      color: #7e7e7e;
  line-height: 28px;
}
.footer-social-icon span {
  color: #fff;
  display: block;
  font-size: 20px;
  font-weight: 700;
  font-family: 'Poppins', sans-serif;
  margin-bottom: 20px;
}
.footer-social-icon a {
  color: #fff;
  font-size: 16px;
  margin-right: 15px;
}
.footer-social-icon i {
  height: 40px;
  width: 40px;
  text-align: center;
  line-height: 38px;
  border-radius: 50%;
}
.facebook-bg{
  background: #3B5998;
}
.twitter-bg{
  background: #55ACEE;
}
.google-bg{
  background: #DD4B39;
}
.footer-widget-heading h3 {
  color: #fff;
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 40px;
  position: relative;
}
.footer-widget-heading h3::before {
  content: "";
  position: absolute;
  left: 0;
  bottom: -15px;
  height: 2px;
  width: 50px;
  background: #ff5e14;
}
.footer-widget ul li {
  display: inline-block;
  float: left;
  width: 50%;
  margin-bottom: 12px;
}
.footer-widget ul li a:hover{
  color: #ff5e14;
}
.footer-widget ul li a {
  color: #878787;
  text-transform: capitalize;
}
.subscribe-form {
  position: relative;
  overflow: hidden;
}
.subscribe-form input {
  width: 100%;
  padding: 14px 28px;
  background: #2E2E2E;
  border: 1px solid #2E2E2E;
  color: #fff;
}
.subscribe-form button {
    position: absolute;
    right: 0;
    background: #ff5e14;
    padding: 13px 20px;
    border: 1px solid #ff5e14;
    top: 0;
}
.subscribe-form button i {
  color: #fff;
  font-size: 22px;
  transform: rotate(-6deg);
}
.copyright-area{
  background: #202020;
  padding: 25px 0;
}
.copyright-text p {
  margin: 0;
  font-size: 14px;
  color: #878787;
}
.copyright-text p a{
  color: #ff5e14;
}
.footer-menu li {
  display: inline-block;
  margin-left: 20px;
}
.footer-menu li:hover a{
  color: #ff5e14;
}
.footer-menu li a {
  font-size: 14px;
  color: #878787;
}



</style>
