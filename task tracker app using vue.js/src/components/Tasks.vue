<template>
    <div :key="task.id" v-for="task in tasks">
        <h3>{{ task.tasktext }}
        </h3>
        <Task @toggle-reminder="$emit('toggle-reminder',task.id)" @delete-task="$emit('delete-task',task.id)" :task="task"/>
    </div>
</template>


<script>
import Task from './Task.vue'
export default{
    // eslint-disable-next-line vue/multi-word-component-names
    name:'Tasks',
    components:{
        Task,
    },
    props:{
        tasks:Array,
    },
    emmit:['delete-task','toggle-reminder']
}
</script>

<style scoped>
    div{
        color: #232323;
    }
    .true{
        color: green;
    }
    .false{
        color: red;
    }
</style>