<template>
    <div v-if="isVisible" class="overlay">
      <div class="form-area">
        <form @submit.prevent="handleSubmit">
          <h2>Create New User</h2>
          <div class="input-group">
            <label for="userName">Name:</label>
            <input type="text" id="userName" v-model="userName" required />
          </div>
  
          <div class="input-group">
            <label for="userEmail">Email:</label>
            <input type="email" id="userEmail" v-model="userEmail" required />
          </div>
  
          <div class="input-group">
            <label for="userAddress">Address:</label>
            <input type="text" id="userAddress" v-model="userAddress" required />
          </div>
  
          <button type="submit">Add User</button>
          <button type="button" @click="closeForm">Close</button>
        </form>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from "vue";
  
  const props = defineProps({
    isVisible: Boolean,
  });
  
  const emit = defineEmits(["close"]);
  
  const userName = ref("");
  const userEmail = ref("");
  const userAddress = ref("");
  
  const closeForm = () => {
    emit("close");
  };
  
  const handleSubmit = () => {
    console.log("User added:", {
      name: userName.value,
      email: userEmail.value,
      address: userAddress.value,
    });
    closeForm();
  };
  </script>
  
  <style scoped>
  .overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);  
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;  
  }
  
  .form-area {
    border: 1px solid #ddd;
    padding: 20px;
    background-color: #fff;  
    border-radius: 8px;  
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);  
    width: 400px;  
  }
  
  .input-group {
    margin-bottom: 15px;
  }
  
  button {
    margin-right: 10px;
  }
  </style>
  