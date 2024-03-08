<template>
  <div class="task-grid">
      <task-uni v-for="task in tasks" :key="task.name" :task="task"></task-uni>
  </div>
</template>

  <script>
 
  import TaskUni from './TaskUni.vue'; 

    export default{
   components:{TaskUni},
      props:{
        tasks:{ type: Array, required: true }
      }
    }
  </script>
  
  
  <style>
    .task-grid{
      display: flex;
      
    }
  </style>
