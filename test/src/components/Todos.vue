<template>
    <div>
        <div v-bind:key="todo.id" v-for="todo in todosss">
            <h3>{{todo.title}}</h3>
            <TodoItem v-bind:todo="todo" v-on:del-todo1="$emit('del-todo2', todo.id)"/>
        </div>         
    </div>
</template>

<script>
import TodoItem from "../components/TodoItem";
export default {
    name: 'Todos',
    components:{
        TodoItem
    },
    props:["todosss"]
}
</script>

<style scoped>

</style>