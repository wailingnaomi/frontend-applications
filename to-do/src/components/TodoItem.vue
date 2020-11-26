<template>
    <!-- binding a class on a condition if todo.completed is true, if todo.completed is true add the class is-complete -->
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox"  v-on:change="markComplete(todo.completed)" v-bind:checked="todo.completed" > <!-- v-on which is used to change an event -->
            <span>{{todo.title}}</span>
            <button @click="$emit('del-todo', todo.id)" class="del">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    data(){
        return{
            todos: this.todo
        }
    },
    methods: {
        markComplete(isComplete) {
            this.todos.completed =! isComplete
        }
    }
}
</script>

<style scoped>
    .todo-item{
        background: #fff;
        color: #333;
        padding: 10px;
        margin-top: 1em;
        border-radius: 10px;

    }

    span{
        margin-left: .5em;
        font-size: 14px;
    }

    .is-complete{
        text-decoration: line-through;
    }

    .del{
        background: #ff6961;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>