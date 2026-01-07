<script setup>
import {ref} from 'vue';

const header = ref('To Do List');

// Reactive array with objects
const tasks = ref([
    {name: 'Do the messages', completed: false},
    {name: 'Washing up', completed: true},
    {name: 'Walk the dog', completed: false},
]);
</script>

<template>
    <h1>{{ header }}</h1>
    <ul>
        <li v-for="task in tasks" :key="task.name">
            {{ task.name }} {{ task.completed ? '(Completed)' : '(Not Completed)' }}
        </li>
    </ul>
</template>
