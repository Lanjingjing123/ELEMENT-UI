<template>
  <div id="app">
    <button @click="passMsg">传你</button>
    <m-parent>
    </m-parent>
  </div>
</template>

<style>
</style>

<script>
import MParent from './views/Parent.vue'
import bus from './util/bus'
export default {
  components:{
    MParent,
  },

  methods: {
    passMsg() {
      console.log("passMsg");
      bus.$emit('msg','I am from app');
    }
  },

}
</script>