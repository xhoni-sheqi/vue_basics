<script setup>
    const props = defineProps(['name','surname'])
</script>
<template>
    <p>{{ props.name }}</p>
    <p>{{ props.surname }}</p>
</template>