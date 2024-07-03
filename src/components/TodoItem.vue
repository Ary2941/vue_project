<script setup>
import { ref } from 'vue'

let id = 0

const newTodo = ref('')
const todos = ref([
    {id: id++, text:"todo 1", done:false},
    {id: id++, text:"todo 2", done:false},
    {id: id++, text:"todo 3", done:false},
])

function addTodo(){
    todos.value.push({id: id++,text:newTodo.value})
    newTodo.value = ''
}

function removeTodo(todo){
    todos.value = todos.value.filter((item)=>item !== todo)
}

</script>

<template>
    <main>
        <h1> ToDo aplication</h1>
    <TheTodo>
            <Todo>
            <form @submit.prevent="addTodo">
            <input v-model="newTodo" required placeholder="newTodo">
            <button> add Todo </button>
        </form>

        <ul>
            <li v-for="todo in todos":key="todo.id">
                <input type="checkbox" v-model="todo.done">
                <span :class="{ done: todo.done}"> {{ todo.text }}  </span> {{todo.done }}
                <button @click="removeTodo(todo)"> remover </button>
            </li>
        </ul>

        </Todo>
    </TheTodo>
    </main>
    
</template>

    
<style>
.done {
  text-decoration: line-through;
}
</style>