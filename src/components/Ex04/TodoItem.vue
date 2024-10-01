<template>
  <div>
    <h1>------- TodoItem Component -------</h1>
    <button @click="handleDelete">Delete</button>
  </div>
</template>
  
  <script setup>
const emit = defineEmits(["deleteTodo"]);
const id = 1;
const handleDelete = () => {
  emit("deleteTodo", id);
};
</script>
  
  <style scoped></style>