<template>
  <h1 class="text-h3 mb-3">{{ msg }}</h1>
  <img alt="Vite logo" width="120" src="@/assets/vite.svg" />
  <img alt="Vue logo" width="120" src="@/assets/vue.png" />
  <img alt="Vuetify logo" width="120" src="@/assets/vuetify.png" />
</template>
<script setup lang="ts">
defineProps<{ msg: string }>()
</script>
