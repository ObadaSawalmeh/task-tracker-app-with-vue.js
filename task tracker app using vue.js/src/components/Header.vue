<template>
    <header>
        <h1></h1>
        <h1>{{title}}</h1>
        <Button text="ADD TASK"/>
        <h1></h1>
    </header>
</template>

<script>
import Button from './Button.vue'
export default{
    // eslint-disable-next-line vue/multi-word-component-names
    name:'Header',
    props:['title'],
    components: {
        Button,
    }
}
</script>
<style scoped>
    header{
        display: flex;
        align-content: center;
        justify-content: space-between;
        margin-bottom:20px;
        width: 100%;
        font-weight: 700;
        color: #232323;
        font-size: 16px;
    }
</style>