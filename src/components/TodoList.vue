<template>
  <ul>
    <TodoItem v-for="(todo, idx) in todos"
      v-bind:todo="todo"
      v-bind:idx="idx"
      @remove-todo="removeTodo"
    />
  </ul>
</template>

<script>
import TodoItem from '@/components/TodoItem'

export default {
  props: ['todos'],
  components: {
    TodoItem
  },
  methods: {
    removeTodo(id) {
      this.$emit('remove-todo', id)
    }
  }
}
</script>

<style scoped>
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>
