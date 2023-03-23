<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="title">
    <button type="submit">Create</button>
  </form>
</template>

<script>
export default {
  name: "AddTodo",
  data:() => {
    return {
      title: ''
    }
  },
  methods: {
    onSubmit() {
      if (this.title.trim()) {
        this.$emit('add-todo', this.title)
        this.title = ''
      }
    }
  }
}
</script>

<style scoped>

</style>
