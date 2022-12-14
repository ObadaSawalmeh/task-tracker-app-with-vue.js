<template>
  <div class="container">
    <Header title="Task Tracker"/>
    <AddTask @add-task="addTask"/>
    <Tasks @delete-task="deleteTask" @toggle-reminder='toggleReminder' :tasks="tasks"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Tasks from './components/Tasks.vue';
import AddTask from './components/AddTask.vue';
export default {
  name: 'App',
  components:{
    Header,
    Tasks,
    AddTask,
  },
  data(){
    return {
      tasks:[],
    }
  },
  methods:{
    deleteTask(id){
      this.tasks=this.tasks.filter(task=>{
        if(task.id!==id){
          return task
        }
      })
    },
    toggleReminder(id){
      this.tasks=this.tasks.map((task)=>task.id===id ? {...task,reminder:!task.reminder } : task ) 
    },
    addTask(task){
      this.tasks=[...this.tasks,task]
    }  
  },
  created(){
    this.tasks=[
      {
        id:1,
        tasktext:'Doctor Appontment',
        day:'24/11/2002 , March , 9:00 PM',
        reminder:true,
      },
      {
        id:2,
        tasktext:'Lesson',
        day:'24/2/2022 , April , 9:00 PM ',
        reminder:true,
      },
      {
        id:3,
        tasktext:'School Class',
        day:'24/11/2002 , May , 9:00 PM',
        reminder:true,
      },
      {
        id:4,
        tasktext:'Football Game',
        day:'24/3/2012 , June , 7:00 PM',
        reminder:false,
      }
    ]
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Work+Sans:wght@400;600;700&display=swap');
#app {
  font-family: 'Work Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: crimson;
  margin-top: 60px;
  height: 100%;
}
.container{
  border: 1px solid #232323;
  padding: 10px;
  border-radius: 10px;
  height: 75%;
}
@media (max-width:400px) {
  #app{
    width: 350px;
  }
}
@media (min-width:600px){
  #app{
    width: 600px;
  }
}
</style>