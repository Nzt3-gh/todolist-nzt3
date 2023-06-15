<script setup lang="ts">
import TodoList from './components/TodoList.vue'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <HelloWorld msg="You did it!"/>
  <TodoList/>
</template>

<style>
TodoList{
  top:fixed 0px;
}
</style>