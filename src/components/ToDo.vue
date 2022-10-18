<script setup>
const props = defineProps(["name", "id"]);
const emit = defineEmits(["remove"]);
</script>

<template>
    <li>{{name}} 
         <button @click="emit('remove', props.id)">X</button>
        </li>
</template>