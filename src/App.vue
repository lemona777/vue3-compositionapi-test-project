<template>
  <div>
    <h1>App</h1>    
    <button @click="increaseCount">버튼</button>
    {{ count }}
    <ChildComp :color="color" :bgColor="bgColor" />
    <button @click="color='red'">change color</button>
  </div>
</template>

<script setup>
import { ref, onMounted, watch } from 'vue';
import ChildComp from './components/ChildComp.vue';

let count = ref(0);
let color = ref('green');
let bgColor = ref('yellow');

onMounted(() => {
  console.log('mounted');
})

const increaseCount = () => {
  count.value++;
}

watch(color, () => {
  console.log('color 변경');
});
</script>

<style scoped>

</style>