<template>

</template>

<script setup lang="ts">
import { nanoid } from 'nanoid';
import type { Column } from '~~/types';
const columns = ref<Column[]>([
    {
        id: nanoid(),
        title: "Create marketing landing page",
        tasks: [],
    },
]);
</script>