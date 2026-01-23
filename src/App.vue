<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import { ref } from 'vue';
const count = ref(0)

console.log(count) // { value: 0 }
console.log(count.value) // 0

count.value++
console.log(count.value) // 1  
function increment() {
  count.value++
}

//data
const name = ref('Rechael');
const href = ref('https://www.scrimba.com');
const disabled = ref(true);
const attibutes = {
  id: 'big_emoji',
  class: 'waving',
};
const coding_years = ref(0);
const getFormattedDate = (date) => {
  const options = {year: 'numeric', month: 'long', day: 'numeric' } ;
  return date.toLocalDateString('en-Uk', options);
};
const username = ref('rechelktyjohnson');
const event = ref('dblclick');
const blockLeave = () =>{
  alert("You can't leave!");
}

 // <h3>Today is {{ getFormattedDate(new Date()) }}</h3>
</script>

<template>
  <span v-bind="attibutes">xx</span>
  <h1>Hi, my name is {{name}} </h1>
  <a :href target="_blank">
    <button :disabled>CLick to visit my favourite website! If you can...</button>
  </a>
  <h2>
     {{  coding_years > 0 
      ? `I have been coding for ${coding_years}  years. `
       : "I'm a newbie." }}</h2>
  <button @click="increment">
    {{ count }}
  </button>
 
</template>