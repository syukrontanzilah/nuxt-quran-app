<script setup>
 const route = useRoute();
 const id = route.params.id
 const URL = `https://quran-api.santrikoding.com/api/surah/${id}`

 const {data: datas} = await useFetch(URL)
console.log('data', datas.value)
</script>

<template>
    <main class="xl:w-[500px] bg-white min-h-screen mx-auto">
    <Header :title="datas.nama"/>

    <div class=" p-6 pt-[90px]">
    <div>jumlah ayat {{ datas.jumlah_ayat }}, nomor surat {{ datas.nomor }}</div>

    <div v-for="(ayat, index) in datas.ayat" :key="index">
    {{ ayat.ar }} <br/>
    {{ ayat.idn }}
    </div>
    </div>
    </main>
</template>



