<template>
    <div class="todo-item" v-bind:class="{'is-completed':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            - <!-- {{todo.id}} -->{{" " + todo.title}}
            <button @click="$emit('del-todo1', todo.id)" class="del">x</button>
            </p>
    </div>
</template>
<script>
export default {
    name: "TodoItem",
    props:["todo"],
    methods:{
        markComplete(){
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>
<style scoped>
.todo-item{
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
}

.is-completed{
    text-decoration: line-through;
}
.del{
    background: #ff0000;
    color: #fff;
    border: none;
    border-radius: 15px;
    padding: 5px 9px;
    cursor: pointer;
    float: right;
}
</style>