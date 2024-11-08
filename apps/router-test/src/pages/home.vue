<template>
  <div class="home">
    <h1>All Destinationss</h1>
    <div class="destinations">
      <router-link v-for="destination in destinations" :key="destination.id" :to="{ name: 'Destination.show', params: { id: destination.id ,slug: destination.slug}}">
        {{ destination.name }}
        <img :src="`/images/${destination.image}`" :alt="destination.name" />
      </router-link>
    </div>

  </div>

</template>

<script setup>
import sourceData from '@/data.json';
import { ref } from 'vue';
import { onMounted } from 'vue';

const destinations = ref(sourceData.destinations)

onMounted(() => {
  console.log("mounted")
})
</script>

<style scoped></style>
