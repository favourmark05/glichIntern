<template>
  <div>
    <!-- <h1>love</h1> -->
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <!-- <div> yes</div> -->
          <h1 class="text-white py-3"> {{ details.name }} </h1>
              <img src="../assets/face.png" class="hero-image shadow-lg rounded img-fluid" alt="hero image">
              <nav>
              <ul class="py-5">
                    <li class="link">HOME</li>
                    <li class="link">ABOUT</li>
                    <li class="img-link">
                      <img src="../assets/in.jpg" style="width: 100px; height: 100px" class="nav-img img-fluid">
                    </li>
                    <li class="link">GALLERY</li>
                    <li class="link">CONTACT</li>
                  </ul>
              </nav>
              <div class="icon-bar float-end">
                <a :href="`https://www.instagram.com/${ details.social_media.instagram }`"><i class="fab fa-instagram"></i></a>
                <a :href="`https://twitter.com/${ details.social_media.twitter }`"><i class="fab fa-twitter-square"></i></a>
                <a :href="`https://www.snapchat.com/${ details.social_media.snapchat }`"><i class="fab fa-snapchat-square"></i></a>
                <a :href="`https://aquil.com/${ details.social_media.email }`"><i class="fas fa-envelope-square"></i></a>
              </div>
          </div>
      </div>
    </div>
    <!-- <h1>love</h1> -->
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      details: {
        name: '',
        social_media: {}
      }
    }
  },
  mounted () {
    axios.get('https://hirng-x2021.glitch.me/api').then((resp) => {
      this.details = resp.data
      console.warn(resp)
    })
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Julius+Sans+One&display=swap');
h1{
 font-family: 'Julius Sans One', sans-serif;
 font-size: 2rem !important;
}
.row > .col {
  /* width: 100%; */
  height: 100vh;
  background: linear-gradient(to right,  #ec0537 50%,#ec0537 45%,#ff3388 50%,#ff3388 100%);
}
.hero-image{
  width: 35rem !important;
}
nav > ul {
  display: flex;
  justify-content:center
}
nav > ul > li {
  list-style-type: none;
  color: white;
  font-family: 'Julius Sans One', sans-serif;
  font-weight: bolder;
  padding: 0 2rem;
}
.nav-img{
  border: 1px solid white;
  border-radius: 100%;
}
.link{
  padding-top: 3rem;
}
.icon-bar{
  position: absolute;
  top: 90%;
  right: 30px;
  transform: translateY(-190%);
  float: right !important;
  /* padding: 0 0 2rem 2rem; */
}
.icon-bar a{
  display: block;
  text-align: center;
  transition: all 0.3s ease;
  color: aliceblue;
  /* float: right; */
  padding: 1.3rem;
}
.fab, .fas  {
  color: white;
  font-size: 2rem !important;
}
.icon-bar > a:hover{
transform: scale(1.5);
/* transition: 0.9s; */
}
</style>
