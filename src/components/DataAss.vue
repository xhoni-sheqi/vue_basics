<script setup>
    // how do i pass data from a compontent parent to far child compontent without using props
    // provide and inject
    // provide share data and methods and make them avaible for parents compontents 
    // inject -> child property that specify which methods wants to receive 

    
    import { provide , ref , watch } from "vue";
    import School from "./School.vue"
    // vue watchers -> update the DOM when underlying data changes 
    // watch(source,callback,options)
    // source -> ref() reactive obj array getter function
    // callback -> facntion is called whenever some data changes 
    // immediate deep flush onTrack onTrigger

    // fetching data from vue js 
    // import the ref
    const data =  ref(null);
    const fetchData = () => {
        fetch('https://jsonplaceholder.typicode.com/todos/9')
        .then((response) => {
            if(!response.ok) {
                throw new Error(`HTTP Error! Status ${response.status}`)
            }
            return response.json()
        })
        .then((responseData) => {
            data.value = responseData;
        })
        .catch((error) => {
            console.error("Errpr fetching data!" , error)
        })
    }


    const msg = ref("Default msg")
    const inputTex = ref("")
    
    watch(inputTex , (newValue, oldValue) => {
        msg.value = `You typed: ${newValue}`;
    });

    provide('studentName', 'Alex');
    provide('studentAge', 20);
    provide('studentLocation', ["Earth","IDK"]);

    
</script>

<template>
    <h1 style="color: red">Data Ass </h1>
    <School />
    <h1>{{ msg }}</h1>
    <input v-model="inputTex" placeholder="Typed something">
    <button @click="fetchData">Fetch</button>
    <h1>API DATA </h1>
    <pre>{{ data }}</pre>

</template>