<template>
    <div class="task" :class="stateClass" @click="$emit('taskStateChanged', task)">
        <span class="close" @click.stop="$emit('taskDeleted', task)">x</span>
        <p>{{task.name}}</p>
    </div>
</template>

<script>
export default {
    props:{
        task: {type: Object, required: true}
    },
    computed:{
        stateClass(){
            return {
                doneFalse: !this.task.done,
                doneTrue: this.task.done
            }
        }
    }
}
</script>

<style scoped>
    .task{
        box-sizing: border-box;
        width: 350px;
        max-width: 80vw;
        height: 150px;
        padding: 10px;
        border-radius: 8px;
        font-size: 2rem;
        font-weight: 300;
        cursor: pointer;
        user-select: none;
        
        display: flex;
        justify-content: center;
        align-items: center;

        position: relative;
    }

    .doneFalse{
        border-left: 12px solid #B73229;
        background-color: #F44336;
    }
    .doneTrue{
        color: #DDD;
        border-left: 12px solid #0A8F08;
        background-color: #4CAF50;
        text-decoration: line-through;
    }

    .doneFalse .close{
        background-color: #B73229;
    }

    .doneTrue .close{
        background-color: #0A8F08;;
    }

    .close{
        position: absolute;
        right: 10px;
        top:10px;
        font-size: 0.9rem;
        font-weight: 600;
        height: 20px;
        width: 20px;
        border-radius: 50%;

        display: flex;
        justify-content: center;
    }
</style>