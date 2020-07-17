<template>
    <div>
        <form @submit="addTodo" >
            <input  type="text" name="title" placeholder="Add Todo.." v-model="title">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>
<script>
import { uuid } from 'vue-uuid';



export default {
    name: "AddTodo",
    data(){
        return{
            title:''
        }
    },
    methods:{
        addTodo: function (e) {
            console.log("addTodo");
            e.preventDefault();
            const newTodo = {            
            id: uuid.v1(),
            /* id: 666, */
            title: this.title,
            completed: false
        }
        //send up to parent
        this.$emit('add-todo', newTodo);
        
        }
    }
}
</script>
<style scoped>
    form{
        display: flex;
    }
    input[type="text"]{
        flex: 10;
        padding: 5px;
    }
    input[type="submit"]{
        flex: 2;
    }
</style>