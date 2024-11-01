<!-- components/Sidebar.vue -->
<template>
  <aside v-if="isDesktop" class="sidebar">
    <div>
      <h2 style="margin-bottom: 0px;">AN LEE</h2>
      <h4 style="margin-top: 0px;">Software Engineer</h4>
    </div>

    <nav>
      <!-- Sidebar content, e.g., links -->
      <ul class="nav-content">
        <li><a href="#home">Overview</a></li>
        <li><a href="#about">Employment History</a></li>
        <li><a href="#contact">Education</a></li>
        <li><a href="#contact">Internships</a></li>
      </ul>
    </nav>
  </aside>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const isDesktop = ref(true);

function updateSidebarVisibility() {
  isDesktop.value = window.innerWidth >= 1024; // Adjust breakpoint as needed
}

onMounted(() => {
  updateSidebarVisibility();
  window.addEventListener('resize', updateSidebarVisibility);
});

onUnmounted(() => {
  window.removeEventListener('resize', updateSidebarVisibility);
});
</script>

<style scoped>
.sidebar {
  width: 250px;
  background-color: #333;
  color: white;
  padding: 15px;
  position: fixed;
  height: 100vh;
  /* Other styling as needed */
}

.sidebar a {
  color: white;
  text-decoration: none;
}

.sidebar ul {
  list-style-type: none;
  padding: 0;
}

.sidebar ul li {
  margin: 10px 0;
}

.nav-content {
  margin-top: 100px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  list-style-type: none;
  padding: 0;
}
</style>
