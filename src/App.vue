<template>
  <div>
    <ParentComponent />
    <ProductParent />
    <CountParent />
    <TodoApp />
    <div>
      <h1>Ứng dụng của tôi</h1>
      <Model modalTitle="Thông báo từ hệ thống" @close="handleCloseModal">
        <p>
          Đây là nội dung của modal. Bạn có thể đóng modal bằng cách nhấn vào
          nút 'Close'.
        </p>
      </Model>
    </div>
    <Cart>
      <template #header> Thông tin sản phẩm </template>
      <template #body>
        Đây là mô tả ngắn gọn về sản phẩm này. Sản phẩm có các tính năng nổi bật
        và giá cả hợp lý.
      </template>
      <template #footer>
        <button @click="viewDetails">Xem chi tiết</button>
      </template>
    </Cart>
    <MessageParent/>
    <ListUser/>
    <BaseButton type="submit" @onclick="handleSubmit">Submit</BaseButton>
    <BaseButton type="button" @onclick="handleClick">Cancel</BaseButton>
    <BaseButton type="reset" @onclick="handleReset">Reset</BaseButton>
  </div>
</template>

<script setup>
import CountParent from "./components/Ex03/CountParent.vue";
import ParentComponent from "./components/Ex01/ParentComponent.vue";
import ProductParent from "./components/Ex02/ProductParent.vue";
import TodoApp from "./components/Ex04/TodoApp.vue";
import Model from "./components/Ex05/Model.vue";
import Cart from "./components/Ex06/Cart.vue";
import MessageParent from "./components/Ex07/MessageParent.vue";
import ListUser from "./components/Ex08/ListUser.vue";
import BaseButton from "./components/Ex09/BaseButton.vue";
const handleSubmit = (event) => {
  console.log("Submitted:", event);
};

const handleClick = (event) => {
  console.log("Canceled:", event);
};

const handleReset = (event) => {
  console.log("Reset:", event);
};
</script>

<style>
</style>