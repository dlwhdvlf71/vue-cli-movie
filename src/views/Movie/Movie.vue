
<template>
     <ul>
        <li v-for="movie in nowplaying" :key="movie.id">
            {{movie.title}}
        </li>
    </ul>
   
</template>


<script>

const movieKey = '2d8280011e977622269e13664d038055';

const axios = require('axios');

export default {
        name : 'movies',
        data () {
            return {
                nowplaying : []
            }
        },
        mounted () {
            axios.get(`https://api.themoviedb.org/3/movie/now_playing?api_key=${movieKey}&language=en-US&page=1`)
            .then(function (response) {
                // handle success
                console.log(response.data.results);

                this.nowplaying = response.data.results;
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            .then(function () {
                // always executed
            });
        }
    
}

</script>