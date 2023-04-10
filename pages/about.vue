<script setup>
    const { data, refresh, pending } = await useLazyFetch('https://api.nuxtjs.dev/mountains')
    function refreshMe(){
        refresh()
    }
</script>

<template>
    <div>
        <div v-if="!pending">Page visits: {{ data.length }}</div>
        <div v-else>Loading...</div>
        <button @click="refreshMe">refresh me</button>
    </div>
</template>