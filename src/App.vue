<script setup lang="ts">
import { ref } from 'vue'
import LeftSidebar from './components/LeftSidebar.vue'
import MainContent from './components/MainContent.vue'
import RightSidebar from './components/RightSidebar.vue'

const currentPage = ref('BTC')
</script>

<template>
  <div class="app-container">
    <header>
      <h1>比特币BTC - 符文批量精造工具</h1>
      <nav>
        <button :class="{ active: currentPage === 'BTC' }" @click="currentPage = 'BTC'">BTC</button>
        <button :class="{ active: currentPage === 'Fractal' }" @click="currentPage = 'Fractal'">Fractal</button>
        <button :class="{ active: currentPage === 'TxAcceleration' }" @click="currentPage = 'TxAcceleration'">交易加速</button>
      </nav>
    </header>
    <div class="content">
      <LeftSidebar />
      <MainContent />
      <RightSidebar />
    </div>
  </div>
</template>

<style>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f0f2f5;
}

.app-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

header {
  background-color: #fff;
  padding: 10px;
  margin-bottom: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

h1 {
  font-size: 24px;
  margin: 0 0 10px 0;
}

nav {
  display: flex;
  gap: 10px;
}

nav button {
  padding: 5px 15px;
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  cursor: pointer;
  font-size: 14px;
}

nav button.active {
  background-color: #1976d2;
  color: white;
}

.content {
  display: flex;
  gap: 20px;
}
</style>