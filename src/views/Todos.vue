<template>
  <div>
    <h2>Todo application</h2>
    <hr>
    <AddTodo @add-todo="addTodo" />
    <TodoList :todos ="todos" @remove-todo="removeTodo" />
  </div>
</template>

<script>
import TodoList from '@/components/TodoList'
import AddTodo from "@/components/AddTodo";

export default {
  name: 'Todos',
  components: {
    AddTodo,
    TodoList
  },
  data: () => {
    return {
      todos: [
        {id: 1, title: 'Купить хлеб', completed: false},
        {id: 2, title: 'Помыть посуду', completed: false},
        {id: 3, title: 'Заработать миллион', completed: true},
      ]
    }
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(title) {
      this.todos.push({id: Date.now(), title: title, completed: false})
    }
  }
}
</script>

<style scoped>

</style>
