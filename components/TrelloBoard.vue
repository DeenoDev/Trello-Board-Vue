<template>
    <div>
        <div v-for="column in columns" key="column.id">
            <header>
                {{ column.title }}
            </header>
            <p v-for="task in column.tasks" :key="column.id"></p>
        </div>
    </div>

</template>

<script setup lang="ts">
import { nanoid } from 'nanoid';
import type { Column } from '~~/types';
const columns = ref<Column[]>([
    {
        id: nanoid(),
        title: "Backlog",
        tasks: [
        {
            title: "Create marketing landing page", 
            createdAt: new Date(),
            id: nanoid(), 
        },
        {
            title: "Create marketing landing page", 
            createdAt: new Date(),
            id: nanoid(), 
        },
        {
            title: "Fix page nav bug", 
            createdAt: new Date(),
            id: nanoid(), 
        },
    ],
    },
        {title: "Selected for Dev", id: nanoid(), tasks:[]},
        {title: "In Progress", id: nanoid(), tasks:[]},
        {title: "QA", id: nanoid(), tasks:[]},
        {title: "Complete", id: nanoid(), tasks:[]},
    
]);
</script>