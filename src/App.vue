<script setup lang="ts">
import { Icon } from '@iconify/vue' 
import { ref } from 'vue';

const isOptionsVisible = ref(false)

const showSelectOptions = () => {
  isOptionsVisible.value = !isOptionsVisible.value
}
</script>

<template>
  <div class="main-element">
    <div class="calculator-card">

      <div class="calculation-area">
        <div class="input-value">
          <label for="value">Valor</label>
          <input type="text" id="value" placeholder="Aqui vai um valor"/>
        </div>

        <div class="input-value">
          <label for="currency">Moeda</label>
          <div class="select" @click="showSelectOptions">
            <p>Dolar americano</p>
            <Icon icon="iconamoon:arrow-down-2-light" style="font-size: 28px;" />
          </div>
          <ul class="options" v-if="isOptionsVisible">
            <li>Item 1</li>
            <li>Item 2</li>
            <li>Item 3</li>
            <li>Item 4</li>
            <li>Item 5</li>
          </ul>
        </div>

        <button class="calculte-btn">Converter em reais</button>
      </div>
      
      <div class="total-area">
        <span>US$ 1 = R$ 4,86</span>
        <h1>486,00 Reais</h1>
      </div>
    
    </div>      
  </div>
</template>

<style scoped>
.main-element {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.main-element .calculator-card {
  border: 2px solid #1D1F4C;
  border-radius: 20px;
  width: 450px;
  height: 500px;
  overflow: hidden;
}

.main-element .calculator-card .calculation-area {
  height: 70%;
  background-color: #141534;
  padding: 50px 65px;
}

.main-element .calculator-card .calculation-area .input-value {
  display: flex;
  flex-direction: column;
  margin-bottom: 20px;
  position: relative;
}

.main-element .calculator-card .calculation-area .input-value label {
  color: #B2B8DE;
  font-size: 10px;
  text-transform: uppercase;
}

.main-element .calculator-card .calculation-area .input-value .select {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.main-element .calculator-card .calculation-area .input-value .select p {
  font-size: 14px;
  color: #858282;
}

.main-element .calculator-card .calculation-area .input-value .options {
  background-color: #0E0F25;
  position: absolute;
  top: 65px;
  left: 3px;
  width: 99%;
}

.main-element .calculator-card .calculation-area .input-value .options li {
  padding: 10px 15px;
  color: #858282;
  cursor: pointer;
}

.main-element .calculator-card .calculation-area .input-value .options li:hover {
  background-color: #1D1F4C;
}

.main-element .calculator-card .calculation-area .input-value .select,
.main-element .calculator-card .calculation-area .input-value input {
  margin-top: 10px;
  height: 44px;
  outline: none;
  border-radius: 6px;
  padding: 0 15px;
  color: aliceblue;
  border: 1px solid #1D1F4C;
  background-color: #0E0F25;
}

.main-element .calculator-card .calculation-area .calculte-btn {
  width: 100%;
  margin-top: 20px;
  height: 44px;
  border: none;
  border-radius: 6px;
  background-color: #2F34AB;
  color: #fff;
  font-weight: 600;
}

.main-element .calculator-card .total-area {
  height: 30%;
  background-color: #1F2151;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.main-element .calculator-card .total-area span {
  color: #858aab;
}

.main-element .calculator-card .total-area h1 {
  margin-top: 10px;
  font-weight: 600;
}
</style>
