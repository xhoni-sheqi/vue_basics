<script setup>
import {inject} from "vue"
    // how do i pass data from a compontent parent to far child compontent without using props
    // provide and inject
    // provide share data and methods and make them avaible for parents compontents 
    // inject -> child property that specify which methods wants to receive 

    const studentName = inject('studentName')
    const studentAge = inject('studentAge')
    const studentLocation = inject('studentLocation')

    
</script>

<template>
    <h1>studentName : {{ studentName }}</h1>
    <h1>studentAge : {{ studentAge }}</h1>
    <h1>studentLocation : {{ studentLocation }}</h1>
</template>