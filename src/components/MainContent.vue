<script setup lang="ts">
import { ref } from 'vue'

const runeId = ref('NOAH•SARK•ANIMALS')
const totalSupply = ref('85149.542')
const currentSupply = ref('1557.475')
const percentage = ref('98.82%')
const pricePerSat = ref('3.3')
const transactionCount = ref('19')
const selectedFee = ref(40)
</script>

<template>
  <div class="main-content">
    <div class="rune-info">
      <h2>RuneID: {{ runeId }}</h2>
      <div class="supply-info">
        <span>总量: {{ totalSupply }}</span>
        <span>当量: {{ currentSupply }} ({{ percentage }})</span>
      </div>
      <div class="price-info">
        <span>价格: {{ pricePerSat }} sats/VB</span>
        <span>交易数: {{ transactionCount }}</span>
      </div>
    </div>
    <div class="fee-selection">
      <h3>选择矿工费：</h3>
      <div class="fee-buttons">
        <button :class="{ active: selectedFee === 40 }" @click="selectedFee = 40">最快 (40 sat/VB)</button>
        <button :class="{ active: selectedFee === 36 }" @click="selectedFee = 36">平均 (36 sat/VB)</button>
        <button :class="{ active: selectedFee === 28 }" @click="selectedFee = 28">偏慢 (28 sat/VB)</button>
        <button :class="{ active: selectedFee === 8 }" @click="selectedFee = 8">自定义 (8 sat/VB)</button>
      </div>
      <div class="custom-fee">
        <label for="custom-fee">设置自定义矿工费：</label>
        <input type="number" id="custom-fee" v-model="selectedFee" min="1" max="100" />
        <span>sat/VB</span>
      </div>
    </div>
    <div class="inscription-tools">
      <h3>铭文工具(WIF私钥):</h3>
      <div class="tool-buttons">
        <button>P2TR (0c1p)</button>
        <button>P2WPKH (0c1p)</button>
      </div>
      <textarea placeholder="请输入WIF" rows="3"></textarea>
    </div>
    <div class="actions">
      <button class="primary-button">开始铭刻</button>
    </div>
  </div>
</template>

<style scoped>
.main-content {
  background-color: #fff;
  padding: 20px;
  flex-grow: 1;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.rune-info, .fee-selection, .inscription-tools {
  margin-bottom: 20px;
}

h2, h3 {
  margin-top: 0;
}

.supply-info, .price-info {
  display: flex;
  justify-content: space-between;
  margin-bottom: 10px;
}

.fee-buttons, .tool-buttons {
  display: flex;
  gap: 10px;
  margin-bottom: 10px;
}

button {
  padding: 5px 10px;
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  cursor: pointer;
}

button.active {
  background-color: #4caf50;
  color: white;
}

.custom-fee {
  display: flex;
  align-items: center;
  gap: 10px;
}

textarea {
  width: 100%;
  margin-top: 10px;
}

.primary-button {
  background-color: #1976d2;
  color: white;
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  cursor: pointer;
}
</style>