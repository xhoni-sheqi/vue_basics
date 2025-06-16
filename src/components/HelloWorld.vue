<script setup>

import {reactive} from "vue"
import {computed , ref} from "vue"
let initialState = reactive({val: {count: 0}, user: ["Jhonny", "Sheqi"]})


  // ref function
  // used to create a reference to a value -> created for ref and make reactive single values you can store what you wnat

  let count1 = ref(0)
  let username = ref("")

  // computed properties -> var that updates itseelf whenever the data it depends on the change

  const firstname = ref("Xhoni");
  const lastname = ref("Sheqi");
  // will give us the most updated version
  const fullName = computed(() => firstname.value + " " + lastname.value)

// javascript logic
  const myMessage = "Yellow World";
  const myTut = "http://localhost:5173/";
  const img = "https://letsenhance.io/static/73136da51c245e80edc6ccfe44888a99/1015f/MainBefore.jpg";
  const img_width = 400;
  const img_height = 200;
  const alt_text = "just and image";

  const changeUser = () =>{
    initialState.user[0] = "root";
    initialState.user[1] = "1234"
  } 

</script>

<template>
  <h1 style="color: red">Basics Of Reactive()</h1>
  <h1>Count: {{ initialState.val.count }}</h1>
  <button @click="initialState.val.count++">Increment</button>
  <button @click="initialState.val.count--">Decrement</button>
  <h3>{{ initialState.user[0] }}</h3>
  <h3>{{ initialState.user[1] }}</h3>
  <button @click="changeUser">Change User To root</button>
 

  <h1>Hello World</h1>
  <!-- Interpolation - Data Binding {{  }} -->
   <!-- You can use a js expression but you can't declare variables -->
  <p>{{ myMessage }}</p>

  <!-- older way : <v-bind:href > -->
  <!-- new way -->
   <h1 style="color: red;">Basics Of Data Binding</h1>
  <a :href="myTut">Local Host</a>
  <br>
  <br>
  <br>
  <img 
    :src="img"
    :alt="alt_text"
    :width="img_width"
    :height="img_height"
  >
  <h1 style="color: red;">Basics of Ref()</h1>
  <h1>Counter 2 : {{ count1 }}</h1>
  <button @click="count1++">+</button>
  <button @click="count1--">-</button>
  <!-- Vue.js Reactivity -->
  <!-- reactive changes on the obj trigger updates in the UI  -->
  <!-- a way to make a obj reactive / you can't store primitive data  -->

  <h1 style="color: red;">Basics Of Computed</h1>
  <p>Username: {{ username }}</p>
  <button @click="username='Jordan'">Add</button>
  <h2> {{ fullName }}</h2>

</template>


<style scoped>
/* style specific to your component  */
</style>