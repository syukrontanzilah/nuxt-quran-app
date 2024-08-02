<script lang="ts" setup>
import { defineProps } from "vue";
const props = defineProps({
    title:{
        type: String,
        required: true
    },
    nomor:{
        type: Number,
        required: true,
    },
    jumlahAyat:{
        type: Number,
        required: true,
    },
    suratArab:{
        type: String,
        required: true,
    },
    turunAyat:{
        type: String,
        required: true
    },
    link:{
        type: String,
        required: true
    }
})
</script>

<template>
    <NuxtLink :to="link" >
    <div class="bg-white rounded-md p-5 border border-slate-100 shadow-md mb-6 cursor-pointer transition hover:bg-slate-100 flex justify-between">
        <div class="flex">
        <div class="border h-10 w-10 rounded-full flex justify-center items-center mr-4">
        {{ nomor }}
        </div>
        <div>
        <div class="text-[16px] font-bold">{{ title }}</div>
        <div class="capitalize text-[13px]">{{ jumlahAyat }} ayat - {{ turunAyat }}</div>        
        </div>

        </div>
        <div class="font-bold text-xl">
        {{ suratArab }}
        </div>
    </div>
</NuxtLink>
</template>
