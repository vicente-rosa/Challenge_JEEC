<template>
  <div class="app">
      <carousel 
        @next="next"
        @prev="prev"
      >
          <carousel-slide v-for="(slide,index) in slides" 
          :key="slide" 
          :index="index"
          :visibleSlide= "visibleSlide"
          :message="message"
          >
          <div v-if="visibleSlide === 0" class="slidedefault">Quanto é 2+2</div>
          <div v-if="visibleSlide === 1" class="slidedefault">
            <input v-model="message" class="caixatexto"/>
          </div>
          <div v-if="visibleSlide === 2" class="slide3">
            <li class="cabecalho">Como distinguir uma alterna de uma gaja normal</li>
            <li class="subt1">Talk by Vicente Rosa</li>
            <li class="texto">Nesta palestra vamos abordar variados pontos todos sobre 
              as varias caracteristicas especificas encontradas 
              em alternas e como saber de antemao a probabilidade de encontrar uma</li>
            </div>
          <div v-if="visibleSlide === 3">
          <img :src="slide" 
          width="600"
          height="auto"/>
          </div>
      </carousel-slide >  

      </carousel>
      
  </div>
  <div v-if="visibleSlide === 0 " class="caixa">
    <p>2+2=4</p>
  </div>
  <div v-if="visibleSlide === 1" class="caixa">
    <p>{{ message }}</p>
    
  </div>

</template>

<script>
import slide3 from './components/slide3.vue';
import image from './assets/challenge.jpg'
import caixa from './components/caixa.vue';
import Carousel from './components/Carousel.vue';
import CarouselSlide from './components/CarouselSlide.vue';
export default{
  data() {
      return {
          slides: [
              caixa,    
              caixa,
              slide3,
              image
          ],
          visibleSlide : 0,
          message: '',
      }
      
  },
  methods: {
      next () {
        if(this.visibleSlide >= this.slides.length - 1) {
          this.visibleSlide = 0;
        }else {
          this.visibleSlide++;
        }
      },
      prev () {
        if(this.visibleSlide <= 0) {
          this.visibleSlide = this.slides.length - 1;
        }else {
          this.visibleSlide--;
        }
      }
  },
  components : {
      Carousel,
      CarouselSlide,
      caixa,
      slide3,
  }


}
</script>

<style>
  .app {
      justify-content: center;
      margin: auto;
      border: 3px ;
      padding: 10px;
      display: flex;
      margin-left: auto;
      margin-right: auto;
      
  }
  .slidedefault {
    font-weight: bold;
    text-align: center; 
    border-radius: 10px;
    width: 620px;
    height: 370px;
    background: black;
    color: white;
    font-size: 5em;
    padding: 100px;    
  }
  .caixatexto {
    width: 400px;
    height: auto;
    font-size: 1em;
  }

</style>




              <!--//'https://picsum.photos/id/236/600/350',
              //'https://picsum.photos/id/235/600/350',
              //'https://picsum.photos/id/234/600/350',
              //'https://picsum.photos/id/233/600/350',
              //'https://picsum.photos/id/232/600/350',-->
              