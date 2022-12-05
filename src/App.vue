<template>
  <div class="container">
    <Header title="Task Tracker" :showAddTask="showAddTask" @toggle-add-task="toggleAddTask" />
    <router-view :showAddTask="showAddTask"></router-view>
    <Footer />
 </div> 
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer
  },
  data(){
    return {
      showAddTask : false
    }
  },
  methods:{
    toggleAddTask(){
      this.showAddTask = !this.showAddTask;
    }
  },
  
}
</script>

<style>
  *{
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  .container{
    max-width:500px;
    margin:30px auto;
    overflow:auto;
    min-height: 300px;
    border:1px solid steelblue;
    padding:30px;
    border-radius: 5px;
  }

  .btn{
    border:none;
    padding:0.5rem 1rem;
    color:white;
    font-size:1rem;
    border-radius:0.5rem;
    cursor:pointer;
  }
</style>
