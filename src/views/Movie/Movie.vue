
<template>
    <div class="wrapper">
        <div class="thumnail-wrapper">
            <ListComponents > </ListComponents>
        </div>
    </div>
</template>

<script>

import ListComponents from '@/components/Movie/Poster/List.vue'

export default {

    name : 'Movie',
    components : {
        ListComponents
    }
    
}
</script>

<style>

    /* .wrapper{
        width:100%; height:100%; background-color: black;
    } */

    .wrapper{
 
        background-color: black;
    }

   

</style>