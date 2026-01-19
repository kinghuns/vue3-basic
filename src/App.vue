<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'

//data
const name = ref('Rechael');
const herf = ref('https://www.scrimba.com');
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
  // <header>
  //   <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

  //   <div class="wrapper">
  //     <HelloWorld msg="You did it!" />
  //   </div>
  // </header>

  // <main>
  //   <TheWelcome />
  // </main>
  <span>xx</span>
  <h1>Hi, my name is NAME </h1>
  <a target="_blank">
    <button>CLick to visit my favourite website! If you can...</button>
  </a>
  <h2>I have been coding for 100 years</h2>
  <h3>Today is 29 February 1993</h3>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
