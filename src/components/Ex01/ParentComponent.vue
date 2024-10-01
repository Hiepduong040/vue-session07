<template>
  <div>
    <h1>Ex01</h1>
    <h3>------- Parent Component -------</h3>
    <p>Parent Company: Rikkei Academy</p>
    <ChildrenComponent :propCompany="company" :propComponent="component"></ChildrenComponent>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import ChildrenComponent from './ChildrenComponent.vue';
    let component = ref("Children");
    let company = ref("Children")
</script>

<style>
</style>