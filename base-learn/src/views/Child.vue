<template>
    <div>
        <h3>Child</h3>
        <h5>{{msgParent}}</h5>
        <h6>{{childMsg}}</h6>
        <button @click="passMsg">走你!</button>
    </div>
</template>

<script>
import bus from '../util/bus'
    export default {
        props: {
            msgParent: {
                type: String,
                default: ''
            },
        },
        data() {
            return {
                childMsg : 'child msg'
            }
        },
        methods: {
            passMsg() {
                this.$emit('showMsg',"I am from Child")
            }
        },
        mounted() {
            console.log("attrs",this.$attrs);
            // 监听 msg 自定义事件，在App.vue 发起的自定义事件
            bus.$on('msg',(val)=>{
                this.childMsg = val
            });
        },
    }
</script>

<style scoped>

</style>