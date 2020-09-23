<template>
    <div>
        <input v-model="id" width="100px" placeholder="아이디" />
        <input v-model="pw" height="100px" placeholder="비밀번호"/>
        <button @click="OnLoginClick()"> 클릭 </button>
    </div>
</template>



<script>
export default {
    
    name : 'Login',
    data () {
        return {
            id : '',
            pw : ''
        }
    },
    methods : {
        OnLoginClick() {
            console.log('test')
            console.log(this.id);
            console.log(this.pw);
        }
    }

}
</script>