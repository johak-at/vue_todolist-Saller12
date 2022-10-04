<script setup>
import { ref } from "vue";
const newItem = ref("");
const list = ref([
]);
function addButton()
{
    list.value.push(newItem.value);
    newItem.value = "";
    
}
function deleteButton(index)
{
list.value.splice(index,1);
}


</script>

<template>
    <h1>ToDoList</h1>
    <button @click="addButton">Add Item!</button>
    <input type="text" placeholder="Input Item" v-model="newItem">
        <ul>
            <li v-for="item in list" :key="item">
                    {{item}}
                    <button @click="deleteButton">X</button>
            </li>
           
        </ul>
</template >

<style>

</style>


