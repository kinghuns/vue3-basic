<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import { ref } from 'vue';

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
  <h3>Today is {{ getFormattedDate(New Date()) }}</h3>
</template>