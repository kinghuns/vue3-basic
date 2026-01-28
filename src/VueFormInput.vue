<script setup>
import { ref } from 'vue'

const checkedNames = ref([]);
const checked = ref(false);
const message = ref('');
const picked = ref('');
const messageMulti = ref('');
const selectedOption = ref('');
const selected = ref([]);

const selectedNew = ref('A');

const options = ref([
  { text: 'One', value: 'A' },
  { text: 'Two', value: 'B' },
  { text: 'Three', value: 'C' }
]) ;
const toggle = ref('no');
const age = ref(null);      



</script>

<template>
 <p>Message is: {{ message }}</p>
<input v-model="message" placeholder="edit me" />

<span>Multiline message is:</span>
<p style="white-space: pre-line;">{{ messageMulti }}</p>
<textarea v-model="messageMulti" placeholder="add multiple lines"></textarea>

<br>
<input type="checkbox" id="checkbox" v-model="checked" />
<label for="checkbox">{{ checked }}</label>

<div>Checked names: {{ checkedNames }}</div>

<input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
<label for="jack">Jack</label>

<input type="checkbox" id="john" value="John" v-model="checkedNames" />
<label for="john">John</label>

<input type="checkbox" id="mike" value="Mike" v-model="checkedNames" />
<label for="mike">Mike</label>

<div>Picked: {{ picked }}</div>

<input type="radio" id="one" value="One" v-model="picked" />
<label for="one">One</label>

<input type="radio" id="two" value="Two" v-model="picked" />
<label for="two">Two</label>

<div>Selected: {{ selectedOption }}</div>

<select v-model="selectedOption">
  <option disabled value="">Please select one</option>
  <option>A</option>
  <option>B</option>
  <option>C</option>
</select>
<div>Selected: {{ selected }}</div>

<select v-model="selected" multiple>
  <option>A Things</option>
  <option>B</option>
  <option>C</option>
</select>

<div>Selected: {{ selectedNew }}</div>

<select v-model="selectedNew">
  <option v-for="option in options" :value="option.value">
    {{ option.text }}
  </option>
</select>
<div>Toggle is: {{ toggle }}</div>
<input
  type="checkbox"
  v-model="toggle"
  true-value="test_yes"
  false-value="test_no" />
  
<input v-model.number="age" />

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