<template>
    <div >
        <draggable 
        v-model="columns"
         group="columns"
         :animation="150"
         handle=".drag-handle"
         item-key="id"
         class="flex gap-4 overflow-x-auto items-start"
         >
        <template #item="{element: column}: {element: Column}">
            <div class="column bg-gray-200 p-5 rounded min-w-[250px]">
              <header class="font-bold mb-4">
                <span class="drag-handle cursor-move"> 🖐️ </span>
                 {{ column.title }}
              </header>
              <TrelloBoardTask v-for="task in column.tasks" 
              :key="task.id"
              :task="task" 
              /> 
            <footer>
                <button class="text-gray-500">
                    Add a Card
                </button>
            </footer>
           </div>
        
         </template>
        </draggable>
    </div>
 </template>   



<script setup lang="ts">
import { nanoid } from 'nanoid';
import type { Column } from '~~/types';
import draggable from "vuedraggable";
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