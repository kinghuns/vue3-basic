<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import { ref } from 'vue';
import { reactive, computed } from 'vue'

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
  // return date.toLocalDateString('en-Uk', options);
  return date.toLocaleDateString('en-US');
};
const username = ref('rechelktyjohnson');
const event = ref('dblclick');
const blockLeave = () =>{
  alert("You can't leave!");
}
const formattedDateOld = new Date();
console.log(formattedDateOld);
// const formattedDateNew = getFormattedDate(formattedDateOld);

// console.log(formattedDateNew);

const author = reactive({
  name: 'John Doe',
  books: [
    'Vue 2 - Advanced Guide',
    'Vue 3 - Basic Guide',
    'Vue 4 - The Mystery'
  ]
})

// 一个计算属性 ref
const publishedBooksMessage = computed(() => {
  return author.books.length > 0 ? 'Yes' : 'No'
})

// const items = ref([{ message: 'Foo' }, { message: 'Bar' }])
// const parentMessage = ref('Parent')
// const items = ref([{ message: 'Foo' }, { message: 'Bar' }])
// const parentMessage = 'Parent'
// const items = [
//   /* ... */
//   aa,bb,dd
// ]
// items.forEach((item, index) => {
//   // 可以访问外层的 `parentMessage`
//   // 而 `item` 和 `index` 只在这个作用域可用
//   console.log(parentMessage, item.message, index)
// })
const myObject = reactive({
  title: 'How to do lists in Vue',
  author: 'Jane Doe',
  publishedAt: '2016-04-10'
})

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
  <!-- <h3>Today is {{ getFormattedDate(new Date(Date.UTC(2012, 11, 20, 3, 0, 0))) }}</h3> -->
  <h3>Today is {{ new Date().toLocaleDateString('zh-Hans') }}</h3>
  <p>Has published books:</p>
  <span>{{ publishedBooksMessage }}</span>
  <br/>
  <button @click="awesome = !awesome">Toggle</button>
  <br />

<h1 v-if="awesome">Vue is awesome!</h1>
<h1 v-else>Oh no 😢</h1>
<ul>
  <li v-for="value in myObject">
    {{ value }}
  </li>
</ul>

</template>