<template>
  <div id="app">
    
   <div class="navbar-fixed">
     <nav class = "white" style = "min-height: 145px">
       <div class="container">
         <section class= " white black-text">
           <div class="container">
             
               <a href="#" class="black-text">
                 <font-awesome-icon icon="phone-volume" /> 08187567421
                 <font-awesome-icon icon="envelope-square" /> tioluwanijoseph@gmail.com
               </a>
            
           </div>
           </section>
    <div class="nav-wrapper">
      <a href="#" class="brand-logo "><img src ='./assets/SAED.jpg'></a>
      <ul id="nav-mobile" class="right hide-on-med-and-down black-text" >
        <li><a href="home.html">Home</a></li>
        <li><a href="services.html">Services</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="works.html">Works</a></li>
        <li><a href="contact.html">Contact</a></li>
      </ul>
    </div>
    </div>
  </nav>
    
 
   </div>
  
  <vue-flux
   :options="vfOptions"
   :images="vfImages"
   :transitions="vfTransitions"
   :captions="vfCaptions"
   ref="slider">

   <template v-slot:preloader>
      <flux-preloader />
   </template>

   <template v-slot:caption>
      <flux-caption />
   </template>

   <template v-slot:controls>
      <flux-controls />
   </template>

   <template v-slot:pagination>
      <flux-pagination />
   </template>

   <template v-slot:index>
      <flux-index />
   </template>
</vue-flux>

<button @click="$refs.slider.showImage('next')">NEXT</button>
  </div>

</template>

<script>
//import slider from './components/slider.vue'
import VueFlux from 'vue-flux';
import {
  
   FluxCaption,
   FluxControls,
   FluxIndex,
   FluxPagination,
   FluxPreloader
} from 'vue-flux';


 
export default {
  name: 'app',
  components: {
   
  VueFlux,
      FluxCaption,
      FluxControls,
      FluxIndex,
      FluxPagination,
      FluxPreloader,
   },

   data: () => ({
      vfOptions: {
         autoplay: true
      },
      vfImages: [ './assets.pic1.jpg', './assets.pic2.jpg', './assets.pic1.jpg' ],
      vfTransitions: [ 'fade', 'cube', 'book', 'wave' ],
      vfCaptions: [
         'Caption for image 1',
         'Caption for image 2',
         'Caption for image 3',
      ],
   }),
}
  


</script>

<style>
.black-text li a{
  color: black;
 }
 
</style>
