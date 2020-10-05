<template>
    <div class="wrapper_thumnail">
        <iframe class="ifr-youtube" :src="'https://www.youtube.com/embed/' + tvkey + '?autoplay=1'" width="100%" height="100%"></iframe>
    </div>
</template>

<script>

const axios = require('axios');
const apiKey = '2d8280011e977622269e13664d038055';

export default {
    name : 'thumnail',
    data : () => {
        return {
            tvkey : String
        }
    },
    mounted() {
      //this.swiper.slideTo(0, 1000, false)

      axios.get(`https://api.themoviedb.org/3/tv/top_rated?api_key=${apiKey}&language=en-US&page=1`)
        .then((response) => {
            // handle success
            axios.get(`https://api.themoviedb.org/3/tv/${response.data.results[0].id}/videos?api_key=${apiKey}&append_to_response=videos`).then((response) => {

                this.tvkey = response.data.results[0].key;

            }).catch((error) => {
                console.log(error);
            }).then(() => {

            })
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
    .wrapper_thumnail{
        height: 56.25vw;
    }

    .ifr-youtube{
        border: none;
    }
</style>