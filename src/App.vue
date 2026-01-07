<template>
    <h1>{{ header }}</h1>
    <ul>
        <li v-for="task in tasks" :key="task.name">
            {{ task.name }} {{ task.completed ? '(Completed)' : '(Not Completed)' }}
            <button @click="complete(task.name)">Toggle</button>
        </li>
    </ul>
</template>

<script setup>
import {ref} from 'vue';

const header = ref('To Do List');

// Reactive array with objects
const tasks = ref([
    {name: 'Do the messages', completed: false},
    {name: 'Washing up', completed: true},
    {name: 'Walk the dog', completed: false},
]);

// function to toggle completed property.
const complete = taskName => {
    const task = tasks.value.find(task => task.name === taskName);
    if (task) {
        task.completed = !task.completed;
    }
};
</script>
