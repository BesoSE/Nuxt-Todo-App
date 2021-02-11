<template>
    <div>
                <ul>
                           
                                <li class="input-group " v-bind:class="{'checked':todo.complete}">   <!-- if todo.complete==true add class -->
                                      <input type="checkbox" class="ch" v-on:change="changeComplete">
                                  <h5  class="tx"> {{todo.title}}</h5>
                                     <button @click="$emit('del-todo',todo.id)" class="del">x</button>
                                      </li>
                                     <hr>
                                    
                   </ul>               
    
         

    </div>
</template>

<script>
    export default {
       props:['todo'] ,
       data(){
           return{
               td:this.todo
           }
       },
       methods:{
           changeComplete(){
               if(this.td.complete==false){
                   this.td.complete=true;
              
               }else{
                    this.td.complete=false;
           
               }
              
             
           }
       }
    }
</script>

<style  scoped>

.checked {
  background: #888;
  color: #fff;
  text-decoration: line-through;
}
  .del {
      border:0px;
    background: #ff0000;
    color: #fff;
    border-radius: 100%;
   position: absolute;
  right: 0;
  top: 0;
  padding: 0.02rem 0.5rem;
  }
  .ch{
      margin-top: 0.5rem;
  }
  .tx{
    margin-left: 2rem;
  }
</style>