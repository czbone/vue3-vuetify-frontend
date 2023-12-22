<template>
  <v-app>
    <v-app-bar color="primary">
      <template v-slot:prepend>
        <router-link to="/">
          <v-avatar><img src="@/assets/logo.svg" /></v-avatar>
        </router-link>
      </template>
      <v-app-bar-title>
        <router-link
          to="/"
          class="text-white"
          style="text-decoration: none; vertical-align: middle"
        >
          {{ title }}
        </router-link>
      </v-app-bar-title>
      <template v-slot:append>
        <router-link
          to="/about"
          class="text-white px-3"
          style="text-decoration: none; vertical-align: middle"
        >
          About
        </router-link>
      </template>
    </v-app-bar>
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>
<script setup lang="ts">
import { ref } from 'vue'
const title = ref(import.meta.env.VITE_APP_TITLE)
</script>
