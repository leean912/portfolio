<template>
  <div class="container">
    <SplashScreen />
    <div class="sidebar">
      <Sidebar />
    </div>
    <!-- <NuxtRouteAnnouncer /> -->
    <!-- <NuxtWelcome /> -->
    <div class="content">
      <h1>Welcome to the homepage</h1>
    </div>
  </div>
</template>

<script setup lang="ts">
import SplashScreen from '~/components/SplashScreen.vue';
import Sidebar from '~/components/Sidebar.vue';

const runtimeConfig = useRuntimeConfig()
const appConfig = useAppConfig()
</script>

<style>
.container {
  display: flex;
}

.sidebar {
  width: 250px;
}

.content {
  flex: 1;
  padding: 0px 50px 0px 50px;
}
</style>