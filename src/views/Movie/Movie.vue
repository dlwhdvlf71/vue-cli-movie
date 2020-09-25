
<template>
    <div class="wrapper">
        <ListComponents> </ListComponents>
    </div>
</template>

<script>

import ListComponents from '@/components/Movie/List.vue'

export default {

    name : 'Movie',
    components : {
        ListComponents
    }
    
}
</script>


<style>

    .wrapper{
        width:100%; height:100%; background-color: black;
    }

</style>