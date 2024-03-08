<template>
  <div>
    <div class="task-grid" v-if="tasks.length">
      <task-uni v-for="(task, id) in tasks" :key="task.name" :task="task" @taskDeleted="$emit('taskDeleted', id)"></task-uni>
    </div>
    <p v-else class="no-task">
        Sem tarefas :)
    </p>
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
      justify-content: center;
      flex-wrap: wrap;
      
    }

    .task-grid .task{
      margin: 10px;
    }

    .no-task{
      color: #AAA;
      font-size: 1.5rem;
    }
  </style>
