<script setup>
import Navigation from "@/components/Navigation.vue";
</script>

<template>
  <div class="app-layout">
    <Navigation></Navigation>
    <router-view></router-view>
  </div>
</template>

<style scoped>
.app-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;

  background-image: url("@/assets/images/background-03.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
}
</style>
