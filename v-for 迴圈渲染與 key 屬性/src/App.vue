<template>
	<p 
	class="text"
	:key="textContent"
	>
	{{ textContent }}
	</p>
	<!-- <p 
	v-for="(value, key, index) in dataList" 
	:key="value"
	>
		<span v-show="key!=='key3'">{{ index }} . {{ key }} : {{ value }}</span>
	</p> -->
</template>

<script setup>
import { ref } from 'vue';

const 
textContent = ref("你好，這是我的練習")
const dataList = {
	key1: "a",
	key2: "b",
	key3: "c",
	key4: "d"
}
setTimeout(() =>{
	textContent.value ="使用vue3+vite開發"
},2000)
</script>

<style>
.text {
	font-size: 40px;
	animation: openin 1s ease-in-out;
}
@keyframes openin {
	0% {
		opacity: 0;
		transform: translateY(20px);
	}
	100% {
		opacity: 1;
		transform: translateY(0px);
	}
}
</style>
