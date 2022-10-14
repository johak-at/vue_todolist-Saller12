<script setup>
import ToDo from "./ToDo.vue";
import { ref, computed } from "vue";
const newItem = ref("");
const filterd_list = computed(() => {
    let result = [];
    for(let i = 0; i < list.value.length; i++)
    {
        if(list.value[i].name.toLowerCase().includes(filter.value.toLowerCase()))      
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
    list.value.push(
        {
        id: Date.now().toString(16),
        name: newItem.value,       
    }
    );
    newItem.value = "";
    
}
function deleteButton(id)
{
    for(let i = 0; i < list.value.length; i++)
    {
        if(list.value[i].id === id)      
        {list.value.splice(i,1);
        }
    }
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
            
            <ToDo 
            v-for="item in filterd_list" 
            :name="item.name" 
            :id="item.id"
            :key="item.id" 
            @remove="deleteButton(id)"></ToDo>
        </ul>
</template >

<style>

</style>


