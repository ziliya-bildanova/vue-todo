<template>
  <div>
    <ul>
      <TodoItem v-for="(todo, i) in todos"
                :key="todo.id"
                :todo="todo"
                :index="i"
                @remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";
export default {
  name: "TodoList",
  components: {TodoItem},
  props: [
      "todos"
  ],
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
