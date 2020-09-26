<template>
    <div class="poster_wrapper">
        <vueper-slides>
            <vueper-slide v-for="(slide, i) in nowPlaying" :key="slide.id" :title="slide.title" :idx="i" >
                <template v-slot:content>
                    <div class="poster">
                        <poster-components :posterPath="slide.poster_path" />
                    </div>
                </template>
            </vueper-slide>
        </vueper-slides>
    </div>
</template>

<script>

import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'

import posterComponents from './Poster.vue'

const axios = require('axios');
const apiKey = '2d8280011e977622269e13664d038055';

export default {
    name : 'List',
    data : function () {
        return {
            nowPlaying : []
        }
    },
    components : {
        posterComponents, VueperSlides, VueperSlide 
    },
    mounted : function () {
        axios.get(`https://api.themoviedb.org/3/movie/now_playing?api_key=${apiKey}&language=en-US&page=`)
        .then((response) => {
            // handle success
            //console.log(response.data.results);
            console.log("now playing")

            this.nowPlaying = response.data.results;
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

<style>

    .poster_wrapper{
        height: 100%;
        /*margin: 20px 20px 0px 20px;*/
        padding:20px;
        text-align: center;
    }
    .poster{
        width:500px; height:100%;
        display: inline-block;
    }

</style>