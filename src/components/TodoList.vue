<script setup lang="ts">
import {ref} from 'vue'
interface Task{
  name:string
  done:number
  id:number
}
var number_of_tasks=0
const tasks=ref<Task[]>([
])
const newTaskName=ref('')
const addTask = () => {
  tasks.value.push({name:newTaskName.value,done:0,id:number_of_tasks})
  number_of_tasks+=1
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
  <ul>
    <il class="ongoing" v-for="task in tasks" :key="task.name">
      <div v-if="task.done==0" class="task">{{ task.id }} {{ task.name }}
        <button @click="doTask(task)" class="dobutton">完了</button>
      </div>
    </il>
  </ul>
  
  <ul>
    <il class="done" v-for="task in tasks" :key="task.name">
      <div v-if="task.done==1" class="task">{{ task.id }} {{ task.name }}</div>
    </il>
  </ul>
  </div>
</template>
<style>
.ongoing{
  color: black;
}
.done{
  color:grey;
}
.task{
  margin: auto;
  padding: 5px;
}


</style>