<template>
  <button @click="showContainer(1)">顯示單向綁定</button>
  <button @click="showContainer(2)">顯示雙向綁定</button>
  <button @click="showContainer(200)">沒畫面</button>
  <div class="container-1" v-if="view ===1">
    <p>資料綁定(單向綁定)</p>
    {{ data }}
  </div>

  <div class="container-2" v-if="view ===2">
    <p>資料綁定(雙向綁定)</p>
    <input type="text" v-model="text">
    <p>{{ text }}</p>
  </div>

  <div  v-if="view !==1 && view !==2">
    暫無畫面
  </div>
  
</template>

<script setup>
import { ref } from 'vue';

const data = "Helle Vue"
const text = ref("123")
const view = ref(1)
const showContainer = (index) =>{
  view.value = index
}

</script>

<style>
.container-1{
  border: 2px solid red;
}
.container-2{
  border: 2px solid skyblue;
}
</style>