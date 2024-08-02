<script setup>
 const route = useRoute();
 const id = route.params.id
 const URL = `https://quran-api.santrikoding.com/api/surah/${id}`

 const {data: datas} = await useFetch(URL)
 console.log('data', datas.value)
</script>

<template>
    <main class="xl:w-[500px] bg-white min-h-screen mx-auto">
        <div class="bg-zinc-100 px-5 py-4 flex items-center justify-between shadow-md fixed w-full xl:w-[500px]">
        <NuxtLink :to=" datas.nomor ===1 ? `/` : `/${datas.nomor-1}`">
       <div class="hover:opacity-[0.8] transition">
            <Icon name="solar:skip-previous-bold-duotone" style="color:green" size="30"/>
        </div>        
        </NuxtLink>
 

        <div class="flex flex-col items-center">
        <div class="font-bold text-green-700">
        {{datas.nomor}}. {{datas.nama_latin}} ({{ datas.nama }})
        </div>
        <div class="text-xs capitalize text-zinc-600">
        {{datas.jumlah_ayat}} ayat - {{datas.tempat_turun}}
        </div>
        </div>

        <NuxtLink :to="datas.nomor === 114? `/` : `/${datas.nomor+1}`">
        <div>
            <Icon name="solar:skip-next-bold-duotone" size="30" style="color:green" />
        </div>        
        </NuxtLink>

   
    </div>

    <div class=" p-6 pt-[90px]">
    <div v-for="(ayat, index) in datas.ayat" :key="index">
    <div class="text-right text-2xl font-bold mb-4 mt-4 font-arabic leading-[60px]">
        {{ ayat.ar }}
    </div>
    <div class="text-[13px]">
 {{ayat.nomor}}. {{ ayat.idn }}    
    </div>
   
    </div>
    </div>

    <NuxtLink to="/" class="bg-slate-300 border shadow-lg h-[70px] w-[70px] rounded-full flex items-center justify-center fixed bottom-4 ml-4">
        <Icon name="ant-design:home-twotone" style="color:green" size="30" />
    </NuxtLink>
    </main>
</template>



