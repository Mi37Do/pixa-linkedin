<template>
<div class="w-72 h-full flex flex-col pr-4 py-4 border-r border-slate-200 my-4 overflow-y-auto overflow-x-hidden">
            <a href="https://pixaviz.vercel.app/" class="w-full h-12 flex items-center gap-4 hover:cursor-pointer">
              <div class="w-10 h-10 relative">
               <img src="@/assets/me.png" class="w-10 h-10 object-cover rounded-lg" alt="">
               <span class="w-3 h-3 bg-green-500 absolute rounded-full -bottom-1 -right-1 outline outline-white"></span>
              </div>
              

              <div class="grow flex flex-col overflow-hidden">
                <span class="capitalize font-semibold text-base truncate">laksari mohammed salah eddine</span>
                <span class="turncate text-slate-400">UI/UX designer, frontend developer</span>
              </div>
            </a>

            <div class="w-full h-10 mt-3 flex flex-col">
                <span class="w-full flex justify-between"><span>Viewed your profile this week</span> <span class="text-primary font-semibold">142</span></span>
                <span class="w-full flex justify-between"><span>Impressions on your post</span> <span class="text-primary font-semibold">783</span></span>
            </div>

            <div class="w-full flex flex-col mt-5 gap-1">
                <button class="btn btn-sm btn-costume rounded-md btn-ghost capitalize flex justify-between">My items <BookMark class="w-5 h-5 fill-slate-600"/></button>
                <button class="btn btn-sm btn-costume capitalize btn-ghost text-[#c5811e] bg-[#c5811e]/10 hover:bg-[#c5811e]/20">try premium for free</button>
            </div>

            <span class="w-full h-px bg-slate-200 mt-5"></span>

            <span class="my-4 text-lg capitalize font-bold text-slate-500">expolre</span>
            <span class="capitalize taxt-base text-slate-500 font-semibold mb-4">recent</span>
            <div class="w-full h-fit">
                <span v-for="i in recent" :key="i.id" class="flex items-center gap-2 capitalize">
                    <UsersIcon v-if="i.type" class="w-3 h-3 fill-slate-600"/>
                    <span v-else class="text-lg font-semibold">#</span> 
                    <span>{{i.title}}</span></span>

                    <button class="btn btn-sm text-xs capitalize btn-ghost ml-2 flex items-center gap-2">show more <angle-down class="w-3 h-3"/></button>
            </div>

            <span class="capitalize taxt-base text-slate-500 font-semibold mb-4 mt-6">groups</span>
            <div class="w-full h-fit">
                <span v-for="i in groups" :key="i.id" class="flex items-center gap-2 capitalize mb-1">
                    <UsersIcon class="w-3 h-3 fill-slate-600"/>
                    <span>{{i.title}}</span></span>
                    <button class="btn btn-sm text-xs capitalize btn-ghost ml-2 flex items-center gap-2">show more <angle-down class="w-3 h-3"/></button>
            </div>
          </div>
</template>

<script setup>
import { ref } from 'vue';
import angleDown from '../../assets/icons/angleDown.vue';
import BookMark from '../../assets/icons/bookMark.vue';
import UsersIcon from '../../assets/icons/usersIcon.vue';

const recent = ref([
    {
        id : 1,
        type : false,
        title : 'UI/UX Design'
    },
    {
        id : 2,
        type : true,
        title : 'designers talk'
    },
    {
        id : 3,
        type : false,
        title : 'algeria startup'
    },
    {
        id : 4,
        type : false,
        title : 'user experience'
    },
    {
        id : 5,
        type : false,
        title : 'vue js 3'
    },
    {
        id : 6,
        type : false,
        title : 'daisyui tailwindcss'
    },
])

const groups = ref([
    {
        id : 1,
        title : 'designers talk'
    },
    {
        id : 2,
        title : 'UI/UX inspiration'
    }
])
</script>

<style lang="scss" scoped>

</style>