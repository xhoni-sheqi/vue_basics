<script setup>
import Child from "./Child.vue";
import Slot from "./Slot.vue";
import Default from "./Default.vue";
import {ref} from "vue";
// conditional ability to display or hide elements on the UI based on condition
// v-if (condition) v-else-if (condition) v-else v-show 

// v-show toggles the visibility of an element based on the thrufines of an expression
// v-show toggles the CSS display v-if remove and add tot the dom

// V-for is used to iterate over an array or and obj and render template for each item in the collection
// acts like a for loop
// keys -> the key helps the dom to identify which elements have changes 


// props 

let name = "Xhoni";
let surname = "Sheqi";


// aka properties aree a way to pass data from a parent component to a child component
const isTrue = false;
const isFalse = false;


let isVisible = ref(true);
let peoples = ref(["Alex","Jorda","Chiara"])

// immutable data defined with const cannot change 

// slot -> space component
// named slot = name and v-slot:name or using the template with #name_slot

// fallback -> default content that is displayed when no content is provided for a particular slot



</script>

<template>
    <h1 style="color: red">Conditional Rendering</h1>
    <p v-if="isTrue">This will show if isTrue is true</p>
    <p v-else-if="isTrue">This will show if isFalse is true</p>
    <p v-else>This will show if nor isTrue and isFalse is Ture</p>


    <p v-show="isVisible">This Will Show based on visibility</p>
    <button @click="isVisible = !isVisible">Toggle</button>

    <h1 style="color: red">V-for // Loops in Vue</h1>
    <p v-for="(person,index) in peoples" :key="index">{{ person }}</p>

    <h1 style="color: red;">Props</h1>

    <Child name="Jordan" />
    <Child :name :surname />

    <h1 style="color: red;">Slot</h1>
    <Slot>
        <h1>Content 1 Slot</h1>
        <h1>Content 2 Slot</h1>
    </Slot>

    <Default />

</template>