<script setup>
    import {ref} from "vue";
    import {computed} from "vue";
    let number = ref(5);
    let number_quadrat = computed(function(){
       if(number.value%2)
       {
           return number.value*number.value;
       }
       else
       {
           return "gerade Zahl"
       }
    });
   
</script>

<template>
    <h3> Computed Demo</h3>
    <input>
    <p>Zahl: {{number}}</p>
    <p>Quadriert: {{number_quadrat}}</p>
    <!--function() kann auch als "() =>" geschrieben werden-->
    <!--<button @click="number++">Add</button>-->
</template>