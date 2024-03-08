<template>
    <div class="new-task">
        <input v-model="name" @keydown.enter="add" type="text" class="form-element" placeholder="Adicione tarefas novas">
        <button class="form-element" @click="add">+</button>
    </div>
</template>

<script>
  export default {
    data(){
        return{
            name:''
        }
    },
    methods:{
        add(){
            this.$emit('taskAdded', {name: this.name})
            this.name = ''
        }
    }
  }
</script>

<style>
    .new-task{
        margin: 35px;
    }

    .form-element{
        outline: none;
        font-size: 1.2rem;
        border: 1px solid #FFF;
        padding: 5px 8px;
        color: #FFF;
    }

    input.form-element{
        width: 500px;
        background: #FFF2;
        border-radius: 5px 0 0 5px;
    }

    button.form-element{
        border-left: none;
        background-color: #2196F3;
        border-radius: 0 5px 5px 0;
        
    }

</style>