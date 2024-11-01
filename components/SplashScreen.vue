<!-- components/LoadingScreen.vue -->
<template>
    <div v-if="isLoading" class="loading-screen">
        <p>Loading...</p> <!-- Customize with an image, spinner, or any content -->
    </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const isLoading = ref(true);

// Automatically hide loading after mounted (you can use an event or router guard for more control)
onMounted(() => {
    setTimeout(() => {
        isLoading.value = false;
    }, 2000); // Adjust the timeout as needed
});
</script>

<style scoped>
.loading-screen {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: white;
    z-index: 9999;
    /* Add additional styles as needed */
}
</style>