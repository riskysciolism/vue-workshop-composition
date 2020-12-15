<template>
  <todo-list v-bind:socketResource="'localhost:3000'"></todo-list>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TodoList from './components/todo-list.vue'

export default defineComponent({
  name: 'App',
  components: {
    TodoList
  }
});
</script>
