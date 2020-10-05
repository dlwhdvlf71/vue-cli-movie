<template>
    <div>

        <swiper ref="mySwiper" class="swiper" :options="swiperOption">
            <swiper-slide v-for="dat in propsDatas" :key="dat.id">
                <img class="swiper-img" :src="'https://image.tmdb.org/t/p/w500' + dat.backdrop_path">
            </swiper-slide>
            <div class="swiper-button-prev" slot="button-prev"></div>
            <div class="swiper-button-next" slot="button-next"></div>
        </swiper>

    </div>
</template>


<script>

import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

export default {
    
    components : {
        Swiper, SwiperSlide 
    },
    props : {
        propsDatas : []
    },
    data() {
      return {
        swiperOption: {
            slidesPerView: 8,
            spaceBetween: 0,
            slidesPerGroup: 5,
            loop: true,
            loopFillGroupWithBlank: true,
            navigation: {
                nextEl: '.swiper-button-next',
                prevEl: '.swiper-button-prev'
            }
        },
        datas : []
      }
    },
    computed: {
      swiper() {
        return this.$refs.mySwiper.$swiper
      }
    },
    mounted() {

    }
}
</script>



<style>
    .swiper-img{
        max-width: 230px;
        min-width: 200px;
        height: auto;
    }
</style>