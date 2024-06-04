<script setup>
  import { ref } from 'vue';
  const todo = ref('');

  const emit = defineEmits(['create-todo']);

  const createTodo = () => {
    emit('create-todo', todo.value);
  };
</script>

<template>
  <form @submit.prevent>
    <div class="input-wrap">
      <input
        required
        type="text"
        placeholder="Enter Your Cruddy"
        v-model="todo"
      />
      <button @click="createTodo()">Create Your Cruddy</button>
    </div>
    <p>{{ todo }}</p>
  </form>
</template>

<style lang="scss" scoped>
  .input-wrap {
    display: flex;
    transition: 350ms ease;
    border: 2px solid #41b080;
    border-radius: 4px;

    &:focus-within {
      box-shadow: 0 -4px 30px -1px rgb(0 0 0 / 0.1),
        0 -2px 40px -2px rgb(0 0 0 / 0.1);
    }

    input {
      width: 100%;
      padding: 8px 6px;
      border: none;

      &:focus {
        outline: none;
      }
    }

    button {
      padding: 8px 16px;
      border: none;
      cursor: pointer;
    }
  }
  button:hover {
    transition: 250ms ease;
  }

  button:not(:hover) {
    transition: 250ms ease;
  }

  input:focus::placeholder {
    color: transparent;
  }
</style>
