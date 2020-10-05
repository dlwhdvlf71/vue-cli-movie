<template>
    <div class="wrappe-_main">
        <ThumnailComponents></ThumnailComponents>

        <div>
            <PopularComponents></PopularComponents>
        </div>
        
    </div>
</template>


<script>

import ThumnailComponents from './Thumnail.vue';
import PopularComponents from './Popular.vue';

export default {
    components : {
        ThumnailComponents,
        PopularComponents
    }
}
</script>



<style>
    .wrapper-main{
        
    }
</style>