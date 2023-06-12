<template>
    <div class="w-full h-fit flex gap-4 mt-4 relative">

        <button class="btn btn-xs btn-square absolute right-0 top-0 btn-ghost">
            <DotsIcon class="w-4 h-4 fill-slate-400"/>
        </button>

        <img :src="comment.userImage" class="w-10 h-10 object-cover rounded-lg flex-none" alt="">
        <div class="grow h-full flex flex-col p-2 -m-2 bg-slate-50 rounded-lg">
            <span class="capitalize font-semibold flex gap-2">{{ comment.user }} <span v-if="author" class="text-xs text-white bg-primary py-0.5 px-2 rounded">author</span></span>
            <span class="text-slate-400 capitalize text-xs flex justify-between mt-1">{{ comment.job }} <span>{{ comment.time }}.</span></span>
            <span class="mt-2">{{ comment.text }}</span>

            <div class="w-full h-8 mt-2 flex items-center gap-2">
                <button class="btn btn-sm px-2 rounded btn-ghost fill-primary text-primary text-xs">
                    <LikeIcon class="w-4 h-4"/>
                    <span>{{ comment.likes }}</span>
                </button>
                <span class="h-6 w-px bg-slate-200"></span>
                <button class="btn btn-sm px-2 rounded btn-ghost fill-primary text-primary text-xs">
                    <CommentIcon class="w-4 h-4"/>
                    <span>{{ comment.replies }}</span>
                </button>
            </div>
        </div>
    </div>
</template>

<script setup>
import CommentIcon from '../../assets/icons/commentIcon.vue';
import DotsIcon from '../../assets/icons/dotsIcon.vue';
import LikeIcon from '../../assets/icons/likeIcon.vue';

const props = defineProps(['comment' , 'author'])
</script>

<style lang="scss" scoped>

</style>