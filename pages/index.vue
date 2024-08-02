<script setup>
useHead({
    title:'Al-Quran - Home',
    meta:[
        {name:'Alquran Alfurqon',
         content:'Amazing alQuran digital'
        }
    ]
})
const URL = 'https://quran-api.santrikoding.com/api/surah';

const {data: datas} = await useFetch(URL)
console.log('data', datas.value)
</script>

<template>
    <main class="xl:w-[500px] bg-white min-h-screen mx-auto">
    <Header title="Quran Al-Furqon"/>

    <div class=" p-6 pt-[90px]">
        <Card 
        v-for="item, index in datas"
        :link="`/${item.nomor}`" 
        :title="item.nama_latin"
        :nomor="item.nomor"
        :suratArab="item.nama"
        :jumlahAyat="item.jumlah_ayat"
        :turunAyat="item.tempat_turun"
        />
    </div>
    </main>
</template>



<style lang="scss" scoped>

</style>