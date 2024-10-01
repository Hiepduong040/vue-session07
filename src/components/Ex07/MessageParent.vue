<template>
  <div>
    <h1>Message Parent Component</h1>
    <MessageChildren @messageSent="handleClick" />
    <p v-if="message">{{ message }}</p>
  </div>
</template>
  
  <script setup>
import { ref } from "vue";
import MessageChildren from "./MessageChildren.vue";

const message = ref("");

const handleClick = (value) => {
  message.value = value;
  alert(message.value);
};
</script>
  
  <style scoped>
h1 {
  margin-bottom: 16px;
  font-size: 18px;
}

p {
  color: #312e2e;
  margin-top: 20px;
}
</style>
<style>
</style>