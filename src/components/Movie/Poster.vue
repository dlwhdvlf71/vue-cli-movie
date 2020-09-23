<template>
    <img width="300px" height="300px" :src="'https://image.tmdb.org/t/p/original' + posterPath" >
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
