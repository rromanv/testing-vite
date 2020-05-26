<template>
  <main class="bg-gray-200 h-screen w-screen flex items-center justify-center">
    <div class="flex w-1/2">
      <input
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
        id="nt"
        type="text"
        v-model="newTodo"
        placeholder="New Todo"
      />
      <button
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 ml-4 rounded focus:outline-none focus:shadow-outline"
        type="button"
        @click="add"
      >
        Add
      </button>
    </div>
    <ul>
      <li v-for="t in todos" :key="t.id">{{ t.name }}</li>
    </ul>
    <p>{{ todos }}</p>
  </main>
</template>

<script>
import { ref, reactive } from 'vue'
export default {
  setup() {
    const newTodo = ref('')
    const todos = reactive([])
    const add = () => todos.push({ id: todos.length, name: newTodo })
    return { newTodo, todos, add }
  },
}
</script>
