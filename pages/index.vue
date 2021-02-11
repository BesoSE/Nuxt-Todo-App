<template>


  <div class="container bg-muted">
      <AddTodo v-on:add-todo="addTodo" />
      <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    
  </div>
 
</template>

<script>

export default {
  data(){
    return{
      todos:[]
    }
  },
  methods:{
    addTodo(newTodo){
 
      this.todos=[...this.todos,newTodo];
  
    },
    deleteTodo(id){
     this.todos= this.todos.filter(todo=> todo.id!=id);
    }
  }

  }
</script>

<style scoped>
.container{
  margin-top:1rem;
  border: 0.2px solid gray;
  padding: 0.5rem;
}

</style>
