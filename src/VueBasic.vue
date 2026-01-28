<script setup>
import { ref } from 'vue'

const counter = ref(0)
const name = ref('Rechael')

function greet(event) {
  alert(`Hello ${name.value}!`)
  // `event` 是 DOM 原生事件
  if (event) {
    alert(event.target.tagName)
  }
}

function say(message) {
  alert(message)
}

function warn(message, event) {
  // 这里可以访问原生事件
  if (event) {
    event.preventDefault()
  }
  alert(message)
}

function onPageDown() {
  alert('Page Down key pressed!')
}

</script>

<template>
 

	<button @click="counter++">Add 1</button>
	<p>The button above has been clicked {{ counter }} times.</p>
  <br>  
  <button @click="greet">Greet</button>
  <br> 
  <button class="button"  @click="say('hello')">Say hello</button>
  <br> 
  <button @click="say('bye')">Say bye</button>
  <br>
  <!-- 使用特殊的 $event 变量 -->
<button @click="warn('Form cannot be submitted yet.', $event)">
  Submit
</button>

<!-- 使用内联箭头函数 -->
<button @click="(event) => warn('Form cannot be submitted yet.', event)">
  Submit
</button>
<br>
<input @keyup.page-down="onPageDown" />

</template>

 <style scoped>
.button {
  background-color: #04AA6D;
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}

.button:hover {
  background-color: green;
}
</style>