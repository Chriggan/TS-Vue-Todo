<script setup lang="ts">
import { ref } from 'vue'
defineProps<{ title: string }>()


const fakeItems = ref([
    {id: 1, task: "Autograf från Sean Banan", completed: false},
    {id: 2, task: "Resa till Amsterdam", completed: false},
    {id: 3, task: "Skaka hand med presidenten", completed: false},
])

</script>

<template>
  <h1>{{ title }}</h1>
  <div>
    <form action="submit" id="new-item-form">
      <input type="text" placeholder="Write your Todo-Item!">
      <button @click="">Add item</button>
    </form>
  </div>
  <div id="uncompleted-items">
    <template v-for="item in fakeItems">
        <div v-if="!item.completed" class="item">
            <h2>{{ item.task }}</h2>
            <button type="button" @click="">X</button>
        </div>
    </template>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
