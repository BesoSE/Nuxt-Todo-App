<template>
    <div>
 <form @submit.prevent="addTodo" class="input-group mb-3">
    <input type="text" placeholder="Add new..." class="form-control add" v-model="title">
     <div class="input-group-append">
    <input type="submit" value="Add todo" class="btn btn-primary">
    </div>
  </form>
    </div>
</template>

<script>

    export default {
        data(){
            return{
               title:'',
               ids:[]
            }
        },
        methods:{
            
            addTodo(){

                if(this.title){
                    var rand;
                  

                   do{
                        rand=Math.floor(Math.random()*1000);
                       
                      
                      
                    }while(this.ids.includes(rand));
                    this.ids=[...this.ids,rand];
                  
                    const newTodo={
                        id:rand,
                        title:this.title,
                        complete:false
                    }
                      this.$emit('add-todo',newTodo);  
                
                      this.title="";
                }
              
           
            }
        }
    }
</script>

<style  scoped>
.add{
   padding: 0.2rem 1.5rem;
   border-radius: 0.3rem;
    margin-right:1.5rem;
}
.btn{
  padding: 0.2rem 0.5rem;
}
</style>