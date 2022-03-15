<template>
  <div class="about">
  <div style="background-color:#2f2f2f;">
    <h1 class="text-white p-4">Gallery</h1>   
  </div>   
    <div class="mx-5">
      <div class="row mt-3 mb-3">
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 0" src="../assets/img/fruit-01.jpg"/>
        </div>
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 1" src="../assets/img/fruit-02.jpg"/>
        </div>
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 2" src="../assets/img/fruit-03.jpg"/>
        </div>
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 3" src="../assets/img/fruit-04.jpg"/>
        </div>
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 4" src="../assets/img/fruit-05.jpg"/>
        </div>
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 5" src="../assets/img/fruit-06.jpg"/>
        </div>
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 6" src="../assets/img/fruit-07.jpg"/>
        </div>
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 7" src="../assets/img/fruit-08.jpg"/>
        </div>
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 8" src="../assets/img/fruit-09.jpg"/>
        </div>
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 9" src="../assets/img/fruit-10.jpg"/>
        </div>
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 10" src="../assets/img/fruit-11.jpg"/>
        </div>
        <div class="col-lg-3 col-md-6 col-sm-12 px-3 mt-3">
            <img class=" img-item" v-on:click="show = !show" @click="currentIndex = 11" src="../assets/img/fruit-12.jpg"/>
        </div>
      </div>
    </div>
    <div v-if="show" name="fade" class="background-fade">      
        <div  class="img-slide img-s" v-for="i in [currentIndex]" :key="i" >
          <a class="prev" @click="prev" href="#">&#10094; </a>
          <div style="display:flex; place-content: flex-end;">
            <button v-on:click="show = !show" class="btn btn-sm btn-light close">X</button>
            <img :src="currentImg" />
          </div>
          <a class="next" @click="next" href="#">&#10095; </a>
        </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      images: [
        { imgSrc: require("../assets//img/fruit-01.jpg") },
        { imgSrc: require("../assets//img/fruit-02.jpg") },
        { imgSrc: require("../assets//img/fruit-03.jpg") },
        { imgSrc: require("../assets//img/fruit-04.jpg") },
        { imgSrc: require("../assets//img/fruit-05.jpg") },
        { imgSrc: require("../assets//img/fruit-06.jpg") },
        { imgSrc: require("../assets//img/fruit-07.jpg") },
        { imgSrc: require("../assets//img/fruit-08.jpg") },
        { imgSrc: require("../assets//img/fruit-09.jpg") },
        { imgSrc: require("../assets//img/fruit-10.jpg") },
        { imgSrc: require("../assets//img/fruit-11.jpg") },
        { imgSrc: require("../assets//img/fruit-12.jpg") },
      ],
      timer: null,
      currentIndex: 0,
      show: false
    };
  },

  mounted: function() {
    this.startSlide();
  },
  methods: {
    startSlide: function() {
      this.timer = setInterval(this.next, 3000);
    },

    next: function() {
      this.currentIndex += 1;
    },
    prev: function() {
      this.currentIndex -= 1;
    }
  },

  computed: {
    currentImg: function() {
      return   this.images[Math.abs(this.currentIndex) % this.images.length].imgSrc;
    }
  }
};

</script>
<style>
.fade-enter-active,
.fade-leave-active {
  transition: all 0.9s ease;
  overflow: hidden;
  visibility: visible;
  position: absolute;
  width:100%;
  opacity: 1;
}

.fade-enter,
.fade-leave-to {
  visibility: hidden;
  width:100%;
  opacity: 0;
}
.background-fade{
  position: fixed; 
  height:100%; 
  width:100%; 
  top:0px; 
  background-color: #00000078; 
  justify-content: center; 
  align-items: center; 
  display:flex;
}
.img-s{
  height:300px; 
  width:500px; 
  display:contents;
}
.close{
  position:fixed;
  border: solid 3px #2f2f2f;
  border-radius: 5px;
}
.close:hover{
  position:fixed;
  border: solid 3px #f5af31;
  color: #f5af31;
  border-radius: 5px;
}
.img-slide img{
  height:400px;
  width:600px;
  border: solid 8px #2f2f2f;
    border-radius: 15px;
}

.prev, .next {
  cursor: pointer;
  width: auto;
  padding: 16px;
  color: rgb(220, 223, 88);
  font-weight: bold;
  font-size: 18px;
  transition: 0.7s ease;
  text-decoration: none;
  user-select: none;
  margin-top:auto;
  margin-bottom:auto;
}

.next {
  border-radius: 0 4px 4px 0;
}

.prev {
  border-radius: 4px 0 0 4px;
}

.prev:hover, .next:hover {
  background-color: rgba(0,0,0,0.9);
}

.img-item{
  border-radius: 3px;
  width: 100%;
  height: 220px;
  box-shadow: 0px 2px 5px #c9c7c7;
  cursor: pointer;
}
.img-slide{
  width: 50%;
}
.banner-fcs{
  background-image: url(../assets/img/banner_fruit.jpg);
  height: 100%; 
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}
  .line{
    width: 15%;
    background-color: #f5af31;
    border: 2px solid #f5af31;
  }
  .curser{
    cursor: pointer;
  }
  @media only screen and (max-width: 768px){
    .img-slide img{
    height:200px;
    width:auto;
    border: solid 8px #2f2f2f;
    border-radius: 15px;
}
  }
</style>