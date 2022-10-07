<script setup>
import { Result } from "postcss";
import { ref, computed } from "vue";
const newItem = ref("");
const filterd_list = computed(() => {
    let result = [];
    for(let i = 0; i < list.value.length; i++)
    {
        if(list.value[i].toLowerCase().includes(filter.value.toLowerCase()))      
        {
            result.push(list.value[i]);
        }
    }
    console.log(result);
    return result;
    
});
let filter = ref("");
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
    <br>
    <input @keyup.enter="addButton()" type="text" placeholder="Input Item" v-model="newItem">
    <br>
    <input type = "text" placeholder ="filter list" v-model="filter">
        <ul>
            <li v-for="(item, index) in filterd_list" :key="item">
                {{index}} - {{item}} 
                    <button @click="deleteButton(index)">X</button>
            </li>
           
        </ul>
</template >

<style>

</style>


