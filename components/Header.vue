<script lang="ts" setup>
import { defineProps } from "vue";
const props = defineProps({
    title:{
        type: String,
        required: true
    }
})
</script>

<template>
    <div class="bg-zinc-100 h-16 flex items-center justify-center font-bold shadow-md fixed w-[500px]">
    {{ title }}
    </div>
</template>
