<template>
  <div>
    <h1>Ex03</h1>
    <h3>------ Parent Component ------</h3>
    Count: {{ count }}
    <CountChildren @increment="increaseCount"></CountChildren>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import CountChildren from './CountChildren.vue';

const count = ref(0); 
 
const increaseCount = ()=>{
    count.value+=1;
}
</script>

<style>

</style>