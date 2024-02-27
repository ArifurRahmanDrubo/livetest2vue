<template>
    <div class="p-4">
      <div v-for="(task, index) in tasks" :key="index" class="flex items-center space-x-4">
        <div>{{ task.name }}</div>
        <div>{{ task.time }}</div>
        <button @click="editTask(task)">Edit</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      tasks: Array,
      editTask: Function
    }
  };
  </script> 
    



  