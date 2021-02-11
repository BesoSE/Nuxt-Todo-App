<template>
    <div>
        <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" v-on:del-todo="$emit('del-todo',todo.id)"/>
    </div>
</template>

<script>
    export default {
        props:['todos']
    }
</script>

<style  scoped>

</style>