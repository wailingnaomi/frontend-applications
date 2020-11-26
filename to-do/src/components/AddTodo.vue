<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Write a new task">
            <input type="submit" value="+" class="btn">
        </form>
    </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid'

export default {
    name: "AddTodo",
    data() {
        return{
            title: ''
        }
    },
    methods: {
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                id: uuidv4(), 
                title: this.title,
            }
            // send up to parent
            this.$emit('add-todo', newTodo);

            this.title = '';
        }
    }
}
</script>

<style scoped>
    form{
        display: flex;
        margin: 2em 0;
    }

    input[type="text"]{
        width: 100%;
        padding: 1em;
        border: none;
        border-radius: 10px;
    }

    input[type="submit"]{
        border-radius: 100px;
    }
</style>