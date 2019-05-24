<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <button @click="$emit('del-todo',todo.id)" class="del">X</button>
            
            
        </p>
        
    </div>
</template>
<script>
export default {
    name:"todoItem",
    props:["todo"],
    methods:{
        markComplete: function(){
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>
<style scoped>
    .todo-item{
        background: lightgray;
        padding: 10px;
        border-bottom: 1px grey dotted;
    }
    .is-complete{
        text-decoration: line-through;
        color: red;
    }
    .del{
        background: red;
        color: antiquewhite;
        border-radius: 50%;
    }
</style>


