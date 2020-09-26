<template>
    <img class="poster_img" :src="'https://image.tmdb.org/t/p/original' + posterPath" >
</template>


<script>
export default {

    props : {
        'posterPath' : {
            type : String
        }
    }
}
</script>

<style>
    .poster_img{
        /*width: 100%; height: 100%;*/
        width: 100%; height: 100%;
    }
</style>
