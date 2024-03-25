<template>


</template>

<script setup lang="ts">
import type {Task} from '~~/types';
import { nanoid } from 'nanoid';

const emit = defineEmits<{
    (e: "add", payload: Task): void;
}>();

const focused = ref(false);
const title = ref("");

function createTask(e: Event){
    if (title.value.trim()){
        e.preventDefault();
        emit("add", {
            title: title.value.trim(),
            createdAt: new Date(),
            id: nanoid(),
        } as Task)
    }

    title.value = "";
}

</script>