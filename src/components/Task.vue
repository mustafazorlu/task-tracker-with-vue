<template>
  <div v-on:dblclick="$emit('toggle-reminder',task.id)" v-bind:class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>
      {{task.text}}
      <i v-on:click="$emit('delete-task',task.id)" class="fas fa-times" v-bind:style="{cursor:p}"></i>
    </h3>
    <p>{{task.day}}</p>
  </div>
</template>

<script>
export default{
  name : 'Task',
  props :{
    task : Object

  },
}
</script>

<style scoped>
  .fas{
    color:red;
  }
  .task{
    background-color: #eee;
    margin:0.5rem;
    padding:0.5rem 1rem;
    
  }

  .task.reminder{
    border-left:0.25rem solid green;
  }

  .task h3{
    display: flex;
    align-items: center;
    justify-content: space-between;

  }
</style>