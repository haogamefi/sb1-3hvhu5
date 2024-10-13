<script setup lang="ts">
import { ref } from 'vue'

const selectedTab = ref('未完成')
</script>

<template>
  <div class="right-sidebar">
    <div class="tabs">
      <button :class="{ active: selectedTab === '未完成' }" @click="selectedTab = '未完成'">未完成</button>
      <button :class="{ active: selectedTab === '已完成' }" @click="selectedTab = '已完成'">已完成</button>
    </div>
    <div class="content">
      <p v-if="selectedTab === '未完成'">没有未完成交易</p>
      <p v-else>没有已完成交易</p>
    </div>
    <div class="fee-info">
      <h3>矿工费UTXO预分</h3>
      <table>
        <tr>
          <td>矿工费</td>
          <td>50.00 0.00000000 BTC</td>
        </tr>
        <tr>
          <td>铭文费用</td>
          <td>50.00 0.00000000 BTC</td>
        </tr>
        <tr>
          <td>服务费</td>
          <td>50.00 0.00000000 BTC</td>
        </tr>
        <tr>
          <td>找零费</td>
          <td>50.00 0.00000000 BTC</td>
        </tr>
        <tr>
          <td>总计</td>
          <td>50.00 0.00000000 BTC</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<style scoped>
.right-sidebar {
  background-color: #fff;
  padding: 20px;
  width: 300px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.tabs {
  display: flex;
  margin-bottom: 20px;
}

.tabs button {
  flex: 1;
  padding: 10px;
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  cursor: pointer;
}

.tabs button.active {
  background-color: #4caf50;
  color: white;
}

.content {
  margin-bottom: 20px;
}

.fee-info table {
  width: 100%;
  border-collapse: collapse;
}

.fee-info td {
  padding: 5px;
  border-bottom: 1px solid #eee;
}

.fee-info tr:last-child td {
  border-bottom: none;
  font-weight: bold;
}
</style>