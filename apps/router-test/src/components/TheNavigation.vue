<template>
    <div id="nav">
        <RouterLink id="logo" to="/">Home</RouterLink>
        <RouterLink v-for="destination in destinations" :to="{name:'Destination.show',params:{id:destination.id,slug:destination.slug}}" :key="destination.id">{{destination.name}}</RouterLink>
        <RouterLink :to="{name:'protect'}">protect</RouterLink>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import sourceData from '@/data.json';

const destinations = ref(sourceData.destinations)
</script>

<style scoped>
    #nav vue-router-link {
        
    }
</style>

