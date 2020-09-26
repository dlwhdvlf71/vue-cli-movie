
<template>
    <div class="wrapper">
        <div class="thumnail-wrapper">
            <ListComponents > </ListComponents>
        </div>
        <div class="first-list-wrapper">
            <TvComponents> </TvComponents>
        </div>
        <div class="second-list-wrapper">2</div>
        <div class="third-list-wrapper">3</div>
    </div>
</template>

<script>

import ListComponents from '@/components/Movie/Poster/List.vue'
import TvComponents from '@/components/Movie/TV/List.vue'

export default {

    name : 'Movie',
    components : {
        ListComponents,
        TvComponents
    }
    
}
</script>

<style>

    /* .wrapper{
        width:100%; height:100%; background-color: black;
    } */

    .wrapper{
        display: grid;
        /* grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(3, 1fr); */
        grid-template-columns: auto auto auto;
        grid-template-rows: 33% 33% 33%;
        grid-gap: 10px;
        background-color: black;
        overflow: hidden;
    }

    .thumnail-wrapper{
        grid-column: span 3;
        overflow: hidden;
    }

    .first-list-wrapper{
        grid-row: 2;
        grid-column: 1;
        height:1000px;
    }

    .second-list-wrapper{
        grid-row: 2;
        grid-column: 2;
    }

    .third-list-wrapper{
        grid-row: 2;
        grid-column: 3;
    }

</style>