<script setup lang="ts">
import { ref } from 'vue'

const items = ref([
  { name: 'ORANGE•PILLS', percentage: 77.15, count: 1999 },
  { name: 'UNCOMMON•GOODS', percentage: 0.00, count: 603 },
  { name: 'CATS•MEMECOIN•BITCOIN', percentage: 0.28, count: 1200 },
  { name: 'GOD•GOD•MAGICAL', percentage: 92.14, count: 756 },
  { name: 'ASSLARPS•ANONYMOUS', percentage: 76.49, count: 2339 },
  { name: 'TURBO•TOAD•RUNE', percentage: 6.78, count: 669 },
  { name: 'WORLD•PEACE•CAT', percentage: 2.27, count: 679 },
  { name: 'SHORT•THE•WORLD', percentage: 40.29, count: 8929 }
])
</script>

<template>
  <div class="left-sidebar">
    <h2>回收文案：</h2>
    <div class="card-container">
      <div v-for="item in items" :key="item.name" class="card">
        <div class="card-header">{{ item.name }}</div>
        <div class="card-body">
          <span class="item-percentage">{{ item.percentage.toFixed(2) }}%</span>
          <span class="item-count">({{ item.count }})</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.left-sidebar {
  background-color: #fff;
  padding: 20px;
  width: 400px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

h2 {
  font-size: 18px;
  margin-top: 0;
  margin-bottom: 20px;
}

.card-container {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.card {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.card-header {
  background-color: #1976d2;
  color: white;
  padding: 10px;
  font-weight: bold;
  font-size: 14px;
}

.card-body {
  padding: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.item-percentage {
  color: #4caf50;
  font-weight: bold;
}

.item-count {
  color: #888;
  font-size: 12px;
}
</style>