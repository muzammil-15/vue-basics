<script setup>
import { ref } from 'vue';



var todos = ref([])
var newTodo = ref("")


const deleteTodo = (id) => {
    todos.value = todos.value.filter(todo => todo.id !== id)
}

const addTodo = () => {
    if (newTodo.value.trim()) {

        todos.value.push({ id: Date.now(), title: newTodo.value })
        newTodo.value = ""
    }

}

</script>

<template>
    <!-- <Todo /> -->

    <div class="w-full h-screen flex justify-center items-center bg-gray-100">


        <div class="w-[450px] h-auto max-h-[600px] mx-auto bg-white p-8 rounded ">
            <!-- header -->
            <h1 class="text-center text-2xl font-bold">Todo List</h1>

            <!-- input field -->

            <div class="rounded flex justify-between items-stretch border mt-4">
                <input v-model="newTodo" type="text" class="outline-none p-2" placeholder="Add a new task">
                <button class="px-4 bg-blue-600 text-white p-2 text-sm cursor-pointer" @click="addTodo">Add
                    Todo</button>

            </div>

            <!-- to list -->
            <div class="w-full flex flex-col gap-2 mt-4">

                <div class="w-full flex justify-between items-center p-2 bg-gray-50 rounded" v-for="todo in todos"
                    :key="todo.id">
                    <p>{{ todo.title }}</p>
                    <button class="bg-red-100 py-1 px-3 cursor-pointer rounded text-sm" @click="deleteTodo(todo.id)">
                        delete</button>

                </div>

            </div>
        </div>

    </div>






</template>
