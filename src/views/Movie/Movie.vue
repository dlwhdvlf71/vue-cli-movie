
<template>
     <ul>
        <li v-for="movie in nowplaying" :key="movie.id">
            {{movie.title}}
        </li>
    </ul>
</template>


<script>
const axios = require('axios')
const movieKey = '2d8280011e977622269e13664d038055';

export default {
    name : 'movies',
    data : function () {
        return {
            nowplaying : []
        }
    },
    mounted : function () {
        /**
         * 1. regular function 를 이용한 방법
         * regular function 를 쓰는 경우 scope 가 변경되어 this.nowPlaying 에 접근이 불가하다.
         * 바깥쪽에 'const 변수명 = this' 선언하여 전역으로 this 를 사용하게 하자
         */
        // const self = this
        // axios.get(`https://api.themoviedb.org/3/movie/now_playing?api_key=${movieKey}&language=en-US&page=1`)
        // .then(function (response) {
        //     self.nowplaying = response.data.results
        // })
        // .catch(function(error) {
        //     // handle error
        //     console.log(error);
        // })

        /**
         * 2. arrow function 를 이용한 방법
         * 참고 URL : https://ko.javascript.info/arrow-functions
         */
        axios.get(`https://api.themoviedb.org/3/movie/now_playing?api_key=${movieKey}&language=en-US&page=1`)
        .then((response) => {
            this.nowplaying = response.data.results
        })
        .catch((error) => {
            // handle error
            console.log(error);
        })
    }
}

</script>