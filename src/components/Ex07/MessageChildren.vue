<template>
  <div>
    <button @click="handleClick">Send message</button>
  </div>
</template>
  
  <script setup>
const emit = defineEmits(["messageSent"]);
const handleClick = () => {
  emit("messageSent", "This is a message from the child component!");
};
</script>
  
  <style scoped>
button {
  background-color: #312967;
  color: white;
  border-radius: 5%;
  padding: 10px 20px;
}

button:hover {
  background-color: #272a66;
}
</style>