<template>
  <form class="add-form" @submit="onSubmit">
    <div class="form-control">
      <label>Task</label>
      <input type="text" name="text" placeholder="Add Text" v-model="text">
    </div>
    <div class="form-control">
      <label>Day & Time</label>
      <input type="text" name="day" placeholder="Add Day & Time" v-model="day">
    </div>
    <div class="form-control form-control-check">
      <label>Set reminder</label>
      <input type="checkbox" name="reminder" v-model="reminder">
    </div>
    <input type="submit" value="Save Task" class="btn btn-block" style="background-color:#663399">
  </form>
</template>

<script>
  export default{
    name : "AddTask",
    data(){
      return{
        text : '',
        day : '',
        reminder : false
      }
    },
    methods:{
      onSubmit(e){
        e.preventDefault();

        if(!this.text){
          alert('Please add a task');
          return;
        }

        const newTask = {
          // id : Math.floor(Math.random() * 100000),
          text: this.text,
          day:this.day,
          reminder:this.reminder
        }

        this.$emit('add-task', newTask);

        this.text = '',
        this.day = '',
        this.reminder = false
      }
    }
  }
</script>

<style>
</style>