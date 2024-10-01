<template>
    <div>
      <h1>User List</h1>
      <button @click="toggleUserForm">Add User</button>
  
      <FormAddUser :isVisible="isFormVisible" @close="toggleUserForm" />
    </div>
  </template>
  
  <script setup>
  import { ref } from "vue";
  import FormAddUser from "./FormAddUser.vue";
  
  const isFormVisible = ref(false);
  
  const toggleUserForm = () => {
    isFormVisible.value = !isFormVisible.value;
  };
  </script>
  
  <style scoped>
  button {
    padding: 12px 24px;
    margin-bottom: 20px;
    background-color: #007bff;
    color: white;
    border: none;
    cursor: pointer;
    border-radius: 5px;
    transition: background-color 0.3s;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  