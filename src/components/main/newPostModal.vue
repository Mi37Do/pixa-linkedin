<template>
    <input type="checkbox" id="newPost" class="modal-toggle" />
    <div class="modal  modal-top pt-20">
    <div class="modal-box rounded-xl flex flex-col gap-4 w-[600px] mx-auto">
        <div class="w-full h-10 flex items-center justify-between">
            <span class="capitalize text-lg font-semibold">new post</span>
            <label for="newPost" class="btn btn-sm btn-square btn-ghost">
                <TimesIcon class="w-5 h-5 fill-slate-400"/>
            </label>
        </div>
        
        <div class="w-full flex items-center">
            <img src="@/assets/me.png" class="w-10 h-10 rounded-md mr-4" alt="">
            <button class="btn btn-sm btn-costume btn-ghost flex items-center gap-2">
                <UserIcon class="w-4 h-4 fill-slate-600"/>
                <span class="capitalize">you</span>
                <AngleDown class="w-4 h-4"/>
            </button>

            <button class="btn btn-sm btn-costume btn-ghost flex items-center gap-2">
                <earthIcon class="w-4 h-4 stroke-slate-600"/>
                <span class="capitalize">anyone</span>
                <AngleDown class="w-4 h-4"/>
            </button>
        </div>

        <div class="w-full h-60 relative">
            <span class="text-xs text-slate-400 absolute bottom-1 right-3">{{text.length}}/3000</span>
            <textarea maxlength="3000" v-model="text" placeholder="Write what do you think" class="block w-full h-full rounded-md border-0 p-3 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-1 focus:ring-inset focus:ring-primary text-sm sm:leading-6 bg-white mt-2"></textarea>
        </div>

        <div class="w-full h-10 mt-2 flex justify-between">
            <div class="flex gap-2">
                <button class="btn btn-sm btn-costume w-10 p-0 btn-ghost fill-slate-500">
                    <PictureIcon class="w-5 h-5"/>
                </button>
                <button class="btn btn-sm btn-costume w-10 p-0 btn-ghost fill-slate-500">
                    <PlayIcon class="w-5 h-5"/>
                </button>
                <button class="btn btn-sm btn-costume w-10 p-0 btn-ghost fill-slate-500">
                    <CalendarIcon  class="w-5 h-5"/>
                </button>
                <button class="btn btn-sm btn-costume w-10 p-0 btn-ghost fill-slate-500">
                    <ArticleIcon  class="w-5 h-5"/>
                </button>
            </div>

            <label for="newPost" class="btn btn-sm btn-costume capitalize btn-primary text-white shadow-2xl shadow-primary/40">post</label>
        </div>

    </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import AngleDown from '../../assets/icons/angleDown.vue';
import TimesIcon from '../../assets/icons/timesIcon.vue';
import UserIcon from '../../assets/icons/userIcon.vue';
import earthIcon from '../../assets/icons/earthIcon.vue';
import PictureIcon from '../../assets/icons/pictureIcon.vue';
import PlayIcon from '@/assets/icons/playIcon.vue';
import CalendarIcon from '../../assets/icons/calendarIcon.vue';
import ArticleIcon from '../../assets/icons/articleIcon.vue';
const text = ref('')

</script>

<style lang="scss" scoped>

</style>