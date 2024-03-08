<template>
    <div class="task" :class="stateClass">
        <span @click="$emit('taskDeleted', task)" class="close">x</span>
        <p>{{ task.name }}</p>
    </div>
</template>

<script>
export default {
    props: {
        task: { type: Object, required: true }
    },
    computed: {
        stateClass() {
            return {
                pending: this.task.pending,
                done: !this.task.pending
            };
        }
    }
}
</script>

<style>
.task {
    position: relative;
    box-sizing: border-box;
    width: 250px;
    height: 100px;
    padding: 10px;
    border-radius: 8px;
    font-size: 1.5rem;
    font-weight: 300;
    cursor: pointer;
    user-select: none;
    display: flex;
    align-items: center;
    justify-content: center;
}

.pending {
    border-left: 12px solid #B73229;
    background-color: #F44336;
}

.done {
    color: #DDD;
    border-left: 12px solid #0A8F08;
    background-color: #4CAF50;
    text-decoration: line-through;
}

.pending .close {
    background-color: #B73229;
}

.done .close {
    background-color: #0A8F08;
}

.close {
    position: absolute;
    right: 10px;
    top: 10px;
    font-size: 1rem;
    font-weight: 700;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>
