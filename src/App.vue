<script setup>
//composite api
import { ref } from 'vue'
 // ref function make the function reactive
//ref creates a reactive variable when the value of the ref is changed,dom will
//change automatically  
const count =ref(0);
const decreaseCount = () => {
  count.value === 0 ? count.value : --count.value
}
const isDark = ref(false)
</script>

<template>
  <div :class="isDark ? 'bg-black' : 'bg-white'">
  <div class="flex justify-end p-2">
    <input type="checkbox" class="toggle" v-model="isDark" @click ="isDark = !isDark"/>
  </div>
 
  <div>
    <h1 class="text-green-700 font-semibold tracking-widest">
      My First Counter Application
    </h1>
  </div>
 
  <div class="flex p-4 space-x-2">
    <button
      @click="decreaseCount"
      class="px-3 py-1 bg-red-600 rounded-lg text-white"
    >
      -
    </button>
    <p class="text-x1 font-semibold">Counter: {{ count }}</p>
    <button
      @click="++count"
      class="px-3 py-1 bg-green-600 rounded-lg text-white"
    >
      +
    </button>
  </div>
</div>
</template>
 

<style scoped></style>
