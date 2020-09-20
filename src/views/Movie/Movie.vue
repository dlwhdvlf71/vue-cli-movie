
<template>
    <ul>
        <li v-for="movie in nowPlaying" :key="movie.id">
            {{movie.title}}
        </li>
    </ul>
</template>


<script>

const axios = require('axios');
const apiKey = '2d8280011e977622269e13664d038055';

export default {

    data : function () {
        return {
            nowPlaying : []
        }
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
</script>>