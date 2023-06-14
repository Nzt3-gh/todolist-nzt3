<script setup lang="ts">

import Clickcounter from './ClickCounter.vue'
import ItemList from './ItemList.vue'
defineProps<{
  msg: string
}>()
</script>

<template>
  <div>
    <h1 >{{ msg }}</h1>
    <Clickcounter />
    <ItemList />
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
