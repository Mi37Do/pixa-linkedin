<template>
    <div class="w-full h-16 px-8 flex-none border-b border-slate-200">
        <div class="w-full h-full flex items-center justify-between">
            <div class="w-72 flex gap-4 items-center">
                <img src="@/assets/LinkedIn_icon.svg" class="h-8" alt="">
                <!-- 
                <input v-model="searchInput" type="text" placeholder="Recherche" class="block w-full h-10 rounded-md border-0 py-1.5 px-12 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-1 focus:ring-inset focus:ring-primary text-sm sm:leading-6 bg-white">  -->

            </div>

            <div class="flex gap-2">

                <button class="btn btn-sm btn-costume w-10 btn-ghost p-0 fill-slate-400 hover:fill-primary transition-all duration-100">
                    <SearchIcon class="w-6 h-6"/>
                </button>

                <button class="btn btn-sm btn-costume w-fit btn-ghost fill-slate-400 hover:fill-primary transition-all duration-100">
                    <HomeIcon class="w-6 h-6 fill-primary"/>
                    <span class="capitalize text-primary font-semibold">home</span>
                </button>

                <button class="btn btn-sm btn-costume w-10 btn-ghost p-0 fill-slate-400 hover:fill-primary transition-all duration-100 relative">
                    <span class="w-4 h-4 bg-red-500 rounded-full absolute top-0 flex items-center justify-center right-0 outline outline-white text-[9px] text-white">4</span>
                    <UsersIcon class="w-6 h-6"/>
                </button>

                <button class="btn btn-sm btn-costume w-10 btn-ghost p-0 fill-slate-400 hover:fill-primary transition-all duration-100">
                    <BagIcon class="w-6 h-6"/>
                </button>

                <button class="btn btn-sm btn-costume w-10 btn-ghost p-0 fill-slate-400 hover:fill-primary transition-all duration-100 relative">
                    <span class="w-4 h-4 bg-red-500 rounded-full absolute top-0 flex items-center justify-center right-0 outline outline-white text-[9px] text-white">9</span>
                    <ChatIcon class="w-6 h-6"/>
                </button>

                <button class="btn btn-sm btn-costume w-10 btn-ghost p-0 mr-8 stroke-slate-400 hover:stroke-primary transition-all duration-100 relative">
                    <span class="w-4 h-4 bg-red-500 rounded-full absolute top-0 flex items-center justify-center right-0 outline outline-white text-[9px] text-white">12</span>
                    <NotificationIcon class="w-6 h-6 "/>
                </button>

                </div>


                <div class="w-80 flex justify-end items-center gap-4">
                    
                    <button class="btn btn-sm btn-costume capitalize btn-ghost text-[#c5811e] bg-[#c5811e]/10 hover:bg-[#c5811e]/20">try premium for free</button>

                    <label for="" class="btn btn-sm btn-costume bg-white w-10 p-0 hover:bg-white shadow-2xl shadow-primary/30">
                        <img src="@/assets/me.png" class="w-8 h-8 rounded object-cover" alt="">
                    </label>
                </div>

                
                
            
        </div>
    </div>
</template>

<script setup>
import BagIcon from '../assets/icons/bagIcon.vue';
import ChatIcon from '../assets/icons/chatIcon.vue';
import HomeIcon from '../assets/icons/homeIcon.vue';
import SearchIcon from '../assets/icons/searchIcon.vue';
import UsersIcon from '../assets/icons/usersIcon.vue';
import NotificationIcon from '../assets/icons/NotificationIcon.vue';

</script>

<style lang="scss" scoped>

</style>