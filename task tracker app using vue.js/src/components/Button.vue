<template>
    <button v-on:click="addTask()">{{text}}</button>
</template>

<script>
export default{
    // eslint-disable-next-line vue/multi-word-component-names
    name:'Button',
    props:['text'],
    methods :{
        addTask(){
            console.log("!");
        }
    }
}
</script>

<style scoped>
    button{
        border: none;
        font-weight: 700;
        font-size: 20px;
        border-radius: 10px;
        background-color: rgb(69, 207, 69);
        color: rgb(255, 255, 255);
        border: 3px solid rgb(69, 207, 69);
        cursor: pointer;
        height: 40px;
        padding:10px 10px;
        margin: auto 0;
        display: flex;
        align-items:center;
        justify-content: center;
    }
</style>