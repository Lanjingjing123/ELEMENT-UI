<template>
  <div id="app">
    <button @click="passMsg">传你</button>
    <m-parent :msga="a" :msgb="b" :msgc="c"> </m-parent>
  </div>
</template>

<style>
</style>

<script>
import MParent from './views/Parent.vue'
import bus from './util/bus'
export default {
  data() {
    return {
      a: 'msga',
      b: 'msgb',
      c: 'msgc'
    }
  },
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