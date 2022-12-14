<template>
    <div @dblclick="$emit('toggle-reminder',task.id)" :class="[task.reminder ? 'reminder' : 'notreminder' , 'task']">
        <h3>
            {{task.text}}
        </h3>
        <p>
            {{task.day}}
            <i @click="onDelete(task.id);" class="fas fa-times" style="cursor:pointer;"></i>
        </p>
    </div>
</template>

<script>
export default{
    // eslint-disable-next-line vue/multi-word-component-names
    name:'Task',
    props:{
        task:Object,

    },
    methods:{
        onDelete(id){
            this.$emit('delete-task',id);
        }
    },
}
</script>

<style scoped>
.task{
    background-color: #f4f4f4;
    margin: 5px;
    padding: 0px 20px;
    cursor: pointer;
    display: flex;
    align-content: center;
    justify-content: center;
}

p{
    width: 100%;
    display: flex;
    align-content: center;
    justify-content: space-between;
    margin: auto;
}
.fas{
    color: red;
    font-size: 18px;
    margin-left: 20px;
}

.reminder{
    border-left: 5px solid green;
}

.notreminder{
    border-left: 5px solid red;
}
</style>