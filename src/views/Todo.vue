<template>
  {{ hello }}
  <input
    v-model="number"
  />
  <TodoItem
    class="todo-item"
    :class="`item${isSelected ? '-selected' : ''}`"
    v-for="item in items"
    :item="item"
    :key="item.id"
    @click="removefunction"
    :onDelete="onDelete"
  />
  <div>
    Total: {{ items.length }}
    Total: {{ todosCount }}
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem'

export default {
  components: {
    TodoItem
  },
  computed: {
    todosCount() {
      return this.items.length
    },
    newTodos() {
      return ''
    }
  },
  data() {
    return {
      hello: 'Hello World!',
      items: [
        { id: 1, name: 'Matong' },
        { id: 2, name: 'Arm' },
        { id: 3, name: 'Pond' },
      ],
    }
  },
  methods: {
    add() {
      this.number = this.number + 1
    },
    addTodo() {
      this.items = [
        ...this.items,
        {
          id: Math.random(10),
          name: ''
        }
      ]
    },
    onDelete(id) {
      console.log(id)
      this.items = this.items.filter(item => item.id !== id)
    }
  },
  // watch: {
    // items() {
    //   this.saveHistory()
    // },
  // }

  // data: () => {(
    
  // )}
}
</script>

<style>
</style>