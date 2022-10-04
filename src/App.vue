<script setup>
// Import your components here:
import HelloJOHAK from "./components/HelloJOHAK.vue";
import ToDoList from "./components/ToDoList.vue";
function hello(){
  alert("Uwe");
}
</script>

<template>
  <!-- Use your components here: -->
  <ToDoList></ToDoList>
  <br>
  <button @click="hello">Click Me!!</button>
  <div>
    <p>
      built with <img src="/vite.svg" alt="vite-logo" /> &
      <img src="/vue.svg" alt="" />
    </p>
  </div>
</template>
