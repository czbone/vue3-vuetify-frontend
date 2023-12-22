<template>
  <v-container fluid>
    <div class="contents">
      <h1 class="text-h3 mb-3">メモリスト</h1>
      <div v-for="(note, index) in notes" :key="index">
        <v-card class="mx-auto mb-3" elevation="3">
          <v-list>
            <v-list-item :title="note">
              <template v-slot:append>
                <v-btn color="error" @click="removeNote(index)" text="削除" />
              </template>
            </v-list-item>
          </v-list>
        </v-card>
      </div>
      <v-text-field v-model="newNote" label="メモを入力" variant="outlined" @keyup.enter="addNote">
        <template v-slot:append>
          <v-btn color="primary" @click="addNote" text="追加" />
        </template>
      </v-text-field>
    </div>
  </v-container>
</template>
<script setup lang="ts">
import { useNoteStore } from '@/stores/note'
import { ref } from 'vue'

const noteStore = useNoteStore()
const notes = noteStore.notes
const newNote = ref('')

const addNote = () => {
  if (newNote.value.trim()) {
    noteStore.addNote(newNote.value)
    newNote.value = ''
  }
}
const removeNote = (index: number) => {
  noteStore.removeNote(index)
}
</script>
<style scoped>
.contents {
  width: 500px;
  margin: 0 auto;
}
</style>
