<script setup lang="ts">
import {ref} from 'vue'
interface Task{
  name:string
  done:number
}
const tasks=ref<Task[]>([
])
const newTaskName=ref('')
const addTask = () => {
  tasks.value.push({name:newTaskName.value,done:0})
}
const doTask = (task: Task)=>{
  task.done=1
}

</script>
<template>
  <div>
    <h1>TodoList</h1>
  <div>
    <input v-model="newTaskName" type="text">
    <button @click="addTask">追加</button>
  </div>
  <div class="ongoing" v-for="task in tasks" :key="task.name">
    <div v-if="task.done==0">タスク名:{{ task.name }}
      <button @click="doTask(task)">完了</button>
    </div>
  </div>
 
  <div class="done" v-for="task in tasks" :key="task.name">
    <div v-if="task.done==1">タスク名{{ task.name }}</div>
  </div>
  </div>
</template>
<style>
.ongoing{
  color: black;
}
.done{
  color:grey;
}

</style>