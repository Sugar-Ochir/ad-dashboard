<template>
  <div>
    <TheMenu v-if="isLoggedIn" />
    <NuxtPage />
  </div>
</template>

<script setup lang="ts">
const isLoggedIn = ref(false)

// Жишээ: Логин шалгах логик — та өөрийн Auth системтэй холбож өөрчлөх хэрэгтэй
// Жишээ нь localStorage, pinia store, useAuth composable зэргээр
if (process.client) {
  const token = localStorage.getItem('authToken') // эсвэл 'user'
  isLoggedIn.value = !!token
}
</script>
