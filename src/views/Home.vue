<script setup>
let cot = $ref(1);
let search = $ref("");
let upper = $computed(() => search.toUpperCase());
const msg = "Hello, Vue!";
function print() {
  console.log(msg);
}

function inc() {
  cot = cot + 2;
}
</script>

<template>
  <h1>Home</h1>
  <p>cot: {{ cot }}</p>
  <input v-model="search" /><br />
  <p>Your input: {{ search }}</p>
  <p :class="upper === search ? 'green' : 'red'">Upper Case: {{ upper }}</p>

  <button @click="search = ''">Clear</button><br />
  <button @click="inc">Click Me</button> <br />
  <button @click="print">Click Me Again</button>
</template>


<style scoped>
input {
  background: #eee;
}
.green {
  color: green;
}
.red {
  color: red;
}
</style>