<template>
    <div class="w-full h-full pl-4 border-l border-slate-200 mt-4 flex flex-col py-4">
    <div class="w-full h-fit flex flex-col gap-4">
        <span class="text-base font-semibold capitalize mb-4 mt-2 flex justify-between items-center">add to your network <span class="text-sm text-primary">see all</span></span>
        <div v-for="i in usersToAdd" :key="i.id" class="w-full h-10 flex gap-4 items-center cursor-pointer">
            <img :src="i.userImage" class="w-10 h-10 object-cover rounded-md" alt="">
            <div class="grow h-full flex flex-col capitalize overflow-hidden">
                <span class="truncate">{{ i.user }}</span>
                <span class="text-slate-400 truncate">{{ i.job }}</span>
            </div>

            <button class="btn btn-sm rounded-md bg-primary right-0 btn-square hover:bg-primary">
                <AddUser class="w-4 h-4 fill-white"/>
            </button>
        </div>

        <span class="w-full h-px bg-slate-200 mt-2"></span>

        <div class="w-full mt-2 flex flex-wrap gap-x-4 gap-y-1 text-slate-500">
            <span>Infos</span>
            <span>Accessibility</span>
            <span>Customer Support</span>
            <span>Terms & Privacy</span>
            <span>Ads Preferences</span>
            <span>Advertisement</span>
            <span>Ads Preferences</span>
        </div>

        <span class="capitalize">designed & developed by : <a href="https://pixaviz.vercel.app/" class="text-primary font-bold">pixaviz.</a></span>
    </div>
    </div>
</template>

<script setup>
import { ref } from "vue";
import AddUser from "@/assets/icons/addUser.vue";

const usersToAdd = ref([
    {
        id : 1,
        user : 'Spencer Selover',
        userImage : 'https://images.pexels.com/photos/428364/pexels-photo-428364.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
        job : 'senior python developer @ pixaviz'
    },
    {
        id : 2,
        user : 'Andrea Piacquadio',
        userImage : 'https://images.pexels.com/photos/774095/pexels-photo-774095.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
        job : 'junior Vuejs developer @ pixaviz'
    },
    {
        id : 3,
        user : 'Godisable Jacob',
        userImage : 'https://images.pexels.com/photos/718978/pexels-photo-718978.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
        job : 'community manager @ pixaviz'
    },
    {
        id : 4,
        user : 'eliot zouaoui',
        userImage : 'https://images.pexels.com/photos/262391/pexels-photo-262391.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
        job : 'Marketing Manager @ pixaviz'
    }
])
</script>

<style lang="scss" scoped>

</style>