<script setup lang="ts">

import TodoList from './TodoList.vue'

defineProps<{
  msg: string
}>()
</script>

<template>
  <div>
    <TodoList/>
  </div>
</template>

<style scoped>
a {
  color : #42b983;
}

h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

</style>
