<template>
    <button
      :type="buttonType"
      class="base-button"
      @click="handleClick"
    >
      <slot></slot> <!-- Sử dụng slot để chèn nội dung -->
    </button>
  </template>
  
  <script setup>
  import { defineProps, defineEmits } from "vue";
  
  const props = defineProps({
    buttonType: {
      type: String,
      default: "button", // Giá trị mặc định cho type
    },
  });
  
  const emit = defineEmits(["onclick"]);
  
  const handleClick = (event) => {
    emit("onclick", event); // Phát sự kiện onclick
  };
  </script>
  
  <style scoped>
  .base-button {
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    background-color: #4caf50; /* Màu nền */
    color: white; /* Màu chữ */
    cursor: pointer;
    transition: background-color 0.3s;
    font-size: 16px; /* Kích thước chữ */
  }
  
  .base-button:hover {
    background-color: #45a049; /* Màu nền khi hover */
  }
  
  .base-button:focus {
    outline: none; /* Ẩn viền khi focus */
  }
  </style>
  