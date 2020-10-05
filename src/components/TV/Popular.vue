<template>
    <div class="wrapper-Popular">
        <h1>
            <div>인기 프로그램</div>
        </h1>
        <div>
            <SwiperComponetns :propsDatas="datas"></SwiperComponetns>
        </div>
    </div>
</template>


<script>

import SwiperComponetns from './Controls/Swiper.vue';

const axios = require('axios');
const apiKey = '2d8280011e977622269e13664d038055';

export default {
    name : 'TVPopular',
    data() {
        return {
            datas : []
        }
    },
    components : {
        SwiperComponetns
    },
    mounted() {
      axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=${apiKey}&language=en-US&page=1`)
        .then((response) => {
            // handle success

            this.datas = response.data.results;

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
    .wrapper-Popular{


    }
</style>