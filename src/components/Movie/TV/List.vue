
<template>
    <swiper ref="mySwiper" class="swiper" :options="swiperOption">
      <swiper-slide v-for="pop in popular" :key="pop.id">
        <img :src="'https://image.tmdb.org/t/p/w500' + pop.backdrop_path">
        
      </swiper-slide>
      <!-- <swiper-slide>Slide 1</swiper-slide>
      <swiper-slide>Slide 2</swiper-slide>
      <swiper-slide>Slide 3</swiper-slide>
      <swiper-slide>Slide 4</swiper-slide>
      <swiper-slide>Slide 5</swiper-slide> -->
  </swiper>
</template>

<script>

import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

const axios = require('axios');
const apiKey = '2d8280011e977622269e13664d038055';

export default {
    name : 'tvpopular',
    components :{
        Swiper, SwiperSlide
    },
    data() {
      return {
        swiperOption: {
          direction: 'vertical',
          pagination: {
            //el: '.swiper-pagination',
            clickable: true
          }
        },
        popular : []
      }
    },
    computed: {
      swiper() {
        return this.$refs.mySwiper.$swiper
      }
    },
    mounted() {
      //this.swiper.slideTo(0, 1000, false)

      axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=${apiKey}&language=en-US`)
        .then((response) => {
            // handle success
            //console.log(response.data.results);
            
            //console.log(response);

            this.popular = response.data.results;

            //this.nowPlaying = response.data.results;
        })
        .catch((error) => {
            // handle error
            console.log(error);
        })
        .then(() => {
            // always executed
        })
    }

}
</script>
