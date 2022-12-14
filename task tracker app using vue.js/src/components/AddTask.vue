<template>
    <form @submit="onSubmit" class="add-form">
        <div class="form-control">
          <label>Task</label>
          <input type="text" v-model="tasktext" name="text" placeholder="Add Task" />
        </div>
        <div class="form-control">
          <label>Day & Time</label>
          <input
            type="text"
            v-model="day"
            name="day"
            placeholder="Add Day & Time"
          />
        </div>
        <div class="form-control form-control-check">
          <label>Set Reminder</label>
          <input type="checkbox" v-model="reminder" name="reminder"/>
        </div>
    
        <input type="submit" value="Save Task" class="btn btn-block" />
      </form>
</template>
    

<script>
export default{
    data(){
        return {
            tasktext:'',
            day:'',
            reminder:false,
        }
    }
    ,methods:{
        onSubmit(e){
            e.preventDefault();
            if(!this.tasktext){
                alert('please enter a task');
                return
            }
            const newTask = {
                id:Math.floor(Math.random()*1000),
                tasktext:this.tasktext,
                day:this.day,
                reminder:this.reminder,
            }
            this.tasktext='',
            this.day='',
            this.reminder='false',
            this.$emit('add-task',newTask);
        }   
    }
}

</script>

<style scoped>
.add-form {
    margin:auto auto 40px auto;
    width: 80%;
  }
  .form-control {
    margin: 20px auto;
  }
  .form-control label {
    display: block;
    font-weight: 700;
  }
  .form-control input {
    width: 80%;
    height: 40px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 17px;
    outline: none;
    border: none;
    background-color: #f4f4f4;;
    padding: 0px 20px;
    color: #232323;
    opacity: .75;
  }
  .form-control-check {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 80%;
   }
  .form-control-check label {
    flex: 1;
    font-weight: 700;
  }
  .form-control-check input {
    flex: 2;
    height: 20px;
  }
  .btn{
    border: none;
    font-weight: 700;
    font-size: 20px;
    border-radius: 10px;
    background-color: rgb(69, 207, 69);
    color: rgb(255, 255, 255);
    border: 3px solid rgb(69, 207, 69);
    cursor: pointer;
    height: 40px;
    padding:0 10px;
    margin: auto auto;
  }
</style>