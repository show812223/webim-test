<script setup>
import { ref, onMounted } from 'vue';

// 生成隨機顏色的函式
const getRandomColor = () => `hsl(${Math.random() * 360}, 80%, 60%)`;

// 建立 10 個隨機顏色的正方形
const boxes = ref([]);

onMounted(() => {
  boxes.value = Array.from({ length: 10 }, () => ({
    color: getRandomColor(),
    originalColor: '',
  }));
  boxes.value.forEach(box => box.originalColor = box.color);
});

// 滑鼠移入變紅
const handleMouseEnter = (box) => {
  box.color = 'red';
};

// 滑鼠移出恢復原色
const handleMouseLeave = (box) => {
  box.color = box.originalColor;
};
</script>

<template>
  <div class="container">
    <div
        v-for="(box, index) in boxes"
        :key="index"
        class="box"
        :style="{ backgroundColor: box.color }"
        @mouseenter="handleMouseEnter(box)"
        @mouseleave="handleMouseLeave(box)"
    ></div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-wrap: wrap; /* 讓正方形自動換行 */
  gap: 10px; /* 設定間距 */
  justify-content: center;
  max-width: 90vw;
  padding: 20px;
}

.box {
  width: 100px;
  height: 100px;
  background-color: gray; /* 預設顏色 */
  transition: background-color 0.3s;
}
</style>
