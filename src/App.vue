<script setup>
  import {ref} from "vue";
  const apiUrl = import.meta.env.VITE_API_URL || 'https://helloggggg.shop';
  const menuCode = ref(0);
  const menu = ref('');

  const findMenu = () => {
   fetch(`${apiUrl}/menus/${menuCode.value}`)
       .then(response => response.json())
        .then(result => menu.value = result);
  }

</script>

<template>
  <h1>Elastic Beanstalk Test</h1>
  메뉴 코드 : <input type="number" v-model="menuCode">
  <button @click="findMenu">조회하기</button>
  <p>{{ menu }}</p>
</template>

<style scoped>

</style>
