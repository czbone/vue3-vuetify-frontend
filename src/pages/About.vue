<template>
  <v-container fluid>
    <div class="contents">
      <HelloWorld msg="Vite + Vue 3 + Vuetify" />
    </div>
  </v-container>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
import HelloWorld from '@/components/HelloWorld.vue'

export default defineComponent({
  components: {
    HelloWorld
  }
})
</script>
<style scoped>
.contents {
  width: 500px;
  margin: 0 auto;
}
</style>
