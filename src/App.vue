<template>

        <h1>Tarefas</h1>
        <new-task @taskAdded="addTask($event)"></new-task>
        <task-grid :tasks="tasks"></task-grid>
</template>

<script>
import TaskGrid from './components/TaskGrid.vue';
import NewTask from './components/NewTask.vue';

export default {
  components: {TaskGrid, NewTask},
  data(){
    return {
      tasks:[]
    }
  },
  methods:{
    addTask(task){
      const sameName = t => t.name == task.name
      const reallyNew = this.tasks.filter(sameName).length == 0

      if(reallyNew && task.name != ''){
  
        this.tasks.push({
          name: task.name,
          pending: task.pending || true
        })
      }else{
        alert('Tarefa já existe ou é vazia')
      }
    }
  }
  
}
</script>

<style>
body{
  background: #000000;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #434343, #000000);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #434343, #000000);
  color: white;
  font-family: Arial, Helvetica, sans-serif;
}

#app {
  display: flex;
  flex: 1;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

#app h1 {
  margin-bottom: 5px;
  font-weight: 300;
  font-size: 24px;
}
</style>