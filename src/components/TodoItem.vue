<template>
  <li>
    <span :class="{done: todo.completed}">
      <input type="checkbox" @change="todo.completed = !todo.completed" :checked="todo.completed">
      <strong>{{ index+1 }}</strong>
      {{ todo.title }}
    </span>
    <button class="rm" @click="$emit('remove-todo', todo.id)">&times;</button>
  </li>
</template>

<script>
export default {
  name: "TodoItem",
  props: {
    todo: {
      type: Object,
      required: true
    },
    index: Number
  }
}
</script>

<style scoped>
  li {
    border: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    padding: .5rem 2rem;
    margin-bottom: 1rem;
  }
  .rm {
    background-color: red;
    color: white;
    border-radius: 50%;
    font-weight: bold;
    border: none;
    cursor: pointer;
  }
  .done {
    text-decoration: line-through;
  }
  input {
    margin-right: 1rem;
  }
</style>

