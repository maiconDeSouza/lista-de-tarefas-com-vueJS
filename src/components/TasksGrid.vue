<template>
    <div class="task-grid">
        <template v-if="tasks.length">
            <Task 
            v-for="(task, i) in tasks" :key="task.name" 
            :task="task" 
            @taskDeleted="$emit('taskDeleted', i)"
            @taskStateChanged="$emit('taskStateChanged', $event)">
                {{task.name}}
            </Task>
        </template>
        <p v-else class="no-task">Sua vida está em Dia :)</p>
    </div>
</template>

<script>
import Task from './Task.vue'
export default {
    components:{Task},
    props:{
        tasks: {type: Array, required: true}
    }
}
</script>

<style scoped>
    .task-grid{
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        gap: 15px;
    }

    
</style>