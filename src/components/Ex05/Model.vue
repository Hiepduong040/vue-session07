<template>
    <div v-if="isVisible" class="modal-overlay">
      <div class="modal-box">
        <div class="modal-header">
          <h3>{{ modalTitle }}</h3>
          <button @click="closeModal" class="btn-close">x</button>
        </div>
        <div class="modal-body">
          <slot></slot> <!-- Sử dụng slot để chèn nội dung -->
        </div>
        <div class="modal-footer">
          <button @click="closeModal" class="btn-close">Close</button>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from "vue";
  
  const props = defineProps({
    modalTitle: {
      type: String,
      required: true,
    },
  });
  
  const emit = defineEmits(["close"]);
  
  const isVisible = ref(true);
  
  const closeModal = () => {
    isVisible.value = false;
    emit("close");
  };
  </script>
  
  <style scoped>
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.6);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .modal-box {
    background-color: white;
    padding: 20px;
    border-radius: 8px;
    width: 350px;
    text-align: center;
  }
  
  .modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .btn-close {
    cursor: pointer;
    background-color: #f0f0f0;
    border: none;
    padding: 5px 10px;
    border-radius: 4px;
  }
  
  .btn-close:hover {
    background-color: #d0d0d0;
  }
  </style>
  