<script setup>
import TheTodo from '../components/TodoItem.vue'
</script>

<template>
  <div class="todo">
    <TheTodo />
</div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
