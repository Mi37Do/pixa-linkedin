<template>
    <div class="dropdown dropdown-top">
    <label tabindex="0" class="btn btn-sm btn-costume px-2 fill-slate-400 btn-ghost hover:fill-primary text-slate-400 hover:text-primary">
        <LikeIcon class="w-5 h-5"/>
        <span class="font-semibold">{{likes}}</span>
    </label>
    <div tabindex="0" class="dropdown-content menu p-2 border border-slate-200 bg-base-100 rounded-lg w-40 mb-1 h-12 flex gap-1">
        <button class="btn btn-sm btn-square btn-ghost fill-primary">
            <likeIcon class="w-5 h-5"/>
        </button>
        <button class="btn btn-sm btn-square btn-ghost fill-red-500 hover:bg-red-50">
            <HeartIcon class="w-5 h-5"/>
        </button>
        <button class="btn btn-sm btn-square btn-ghost fill-green-500 hover:bg-green-50">
            <LightBlub class="w-5 h-5"/>
        </button>
        <button class="btn btn-sm btn-square btn-ghost fill-amber-500 hover:bg-amber-50">
            <LaughingIcon class="w-5 h-5"/>
        </button>
    </div>
    </div>
</template>

<script setup>
import HeartIcon from '../../assets/icons/heartIcon.vue';
import LaughingIcon from '../../assets/icons/laughingIcon.vue';
import LightBlub from '../../assets/icons/lightBlub.vue';
import LikeIcon from '../../assets/icons/likeIcon.vue';

const props = defineProps(['likes'])
</script>

<style lang="scss" scoped>

</style>