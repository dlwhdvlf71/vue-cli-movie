<template>
    <div class="wrappe-_main">
        <ThumnailComponents></ThumnailComponents>
        <div>
            <PopularComponents></PopularComponents>
        </div>
        <div>
            <AiringTodayComponents></AiringTodayComponents>
        </div>
        <div>
            <OnTheAirComponents></OnTheAirComponents>
        </div>
    </div>
</template>


<script>

import ThumnailComponents from './Thumnail.vue';
import PopularComponents from './Popular.vue';
import AiringTodayComponents from './AiringToday.vue';
import OnTheAirComponents from './OnTheAir.vue';

export default {
    components : {
        ThumnailComponents,
        PopularComponents,
        AiringTodayComponents,
        OnTheAirComponents
    }
}
</script>



<style>
    .wrapper-main{
        
    }
</style>