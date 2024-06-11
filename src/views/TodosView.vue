<script setup>
  import { ref } from 'vue';
  import TodoCreator from '../components/TodoCreator.vue';

  const todoList = ref([]);

  const createTodo = (todo) => {
    todoList.value.push({
      id: crypto.randomUUID(),
      todo,
      isCompleted: null,
      isEditing: null,
    });
  };
</script>

<template>
  <main>
    <h1>Create a Cruddy</h1>
    <TodoCreator @create-todo="createTodo" />
  </main>
</template>

<style lang="scss" scoped>
  main {
    display: flex;
    flex-direction: column;
    max-width: 500px;
    width: 100%;
    margin: 0 auto;
    padding: 40px 16px;

    h1 {
      margin-bottom: 16px;
      text-align: center;
    }
  }
</style>
