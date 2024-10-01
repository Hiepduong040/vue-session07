<template>
  <div>
    <h3>------- {{ props.propComponent }} Component -------</h3>
    <p>{{ props.propCompany }} Company: Rikkei Academy</p>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';
 const props = defineProps([":propCompany" ,"propComponent"])
</script>

<style>
</style>