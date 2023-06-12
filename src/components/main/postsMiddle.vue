<template>
    <div class="w-full h-full overflow-auto py-4">
        <div class="w-full h-full flex flex-col gap-4">
            <div class="w-full h-fit bg-white outline-1 outline-slate-200 rounded-lg p-4 flex flex-col gap-4">
                <div class="w-full flex gap-4 h-10 overflow-hidden">
                    <img src="@/assets/me.png" alt="" class="w-10 h-10 rounded-md">
                    <label for="newPost" class="btn btn-sm btn-costume grow rounded-md flex justify-start capitalize text-slate-400 bg-white hover:bg-white hover:border-primary hover:text-primary transition-all duration-100">
                        new post
                    </label>
                </div>

                <div class="w-full h-10 flex">
                    <div class="w-10 h-10 mr-4"></div>

                    <div class="grow flex justify-between">
                    <button class="btn btn-sm btn-costume w-fit rounded-md btn-ghost px-2">
                        <PictureIcon class="w-6 h-6 fill-primary"/>
                        <span class="capitalize text-primary">post picture</span>
                    </button>
                    <button class="btn btn-sm btn-costume w-fit rounded-md btn-ghost px-2">
                        <PlayIcon class="w-6 h-6 fill-primary"/>
                        <span class="capitalize text-primary">post video</span>
                    </button>

                    <button class="btn btn-sm btn-costume w-fit rounded-md btn-ghost px-2">
                        <CalendarIcon class="w-6 h-6 fill-primary"/>
                        <span class="capitalize text-primary">create event</span>
                    </button>

                    <button class="btn btn-sm btn-costume w-fit rounded-md btn-ghost px-2">
                        <ArticleIcon class="w-6 h-6 fill-primary"/>
                        <span class="capitalize text-primary">write article</span>
                    </button>
                    </div>
                </div>
            </div>

            <div class="w-full h-8 flex items-center -mt-2">
                <span class="grow h-px bg-slate-200 mr-2"></span>
                <span>Sort by:</span>
                <button class="btn btn-sm w-fit capitalize font-semibold flex ga-4 items-center rounded-md btn-ghost ml-2">top <AngleDown class="w-5 h-5 fill-slate-600"/></button>
            </div>

            <div class="w-full h-fit flex flex-col gap-4 -mt-2">
                <postCard :post="i" v-for="i in posts" :key="i"/>
                <div class="h-24 flex-none">
                    <div class="w-full h-full flex justify-center items-center">
                        <span class="loading loading-ring loading-md"></span>
                    </div>
                </div>
                </div>
            
        </div>
    </div>
</template>

<script setup>
import PictureIcon from '@/assets/icons/pictureIcon.vue'
import PlayIcon from '@/assets/icons/playIcon.vue'
import CalendarIcon from '@/assets/icons/calendarIcon.vue';
import ArticleIcon from '@/assets/icons/articleIcon.vue';
import AngleDown from '@/assets/icons/angleDown.vue';

import postCard from './postCard.vue'
import { ref } from 'vue';


const posts = ref([
    {
        id: 1,
        user: 'Elen Yakova',
        job: 'Graphic Designer',
        time:'20min',
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas accusamus cumque unde autem assumenda. Ullam et explicabo sit! Molestias delectus alias magni exercitationem similique iure quia tenetur? Mollitia porro dolores itaque in officia culpa pariatur, quasi iusto',
        likes: '124',
        comments : '26',
        userImage : 'https://images.pexels.com/photos/91227/pexels-photo-91227.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
        postImages : [
            {
                id:1,
                url :'https://mir-s3-cdn-cf.behance.net/project_modules/1400/7f0cd8145756577.62a3af133aeaf.jpg'
            }    
        ],
        link: 'https://www.behance.net/gallery/145756577/Freshka-Packaging-and-Logo-Design'

    },

    {
        id: 2,
        user: 'sara sushi',
        job: 'frontend developer',
        time:'1h',
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas accusamus cumque unde autem assumenda. Ullam et explicabo sit! Molestias delectus alias magni exercitationem similique iure quia tenetur? Mollitia porro dolores itaque in officia culpa pariatur, quasi iusto',
        likes: '447',
        comments : '12',
        userImage : 'https://images.pexels.com/photos/871495/pexels-photo-871495.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
        postImages : [
            {
                id:1,
                url :'https://mir-s3-cdn-cf.behance.net/project_modules/max_1200/186a17143037215.6272c1c0a2578.png'
            }    
        ],
        link: 'https://www.behance.net/gallery/143037215/Ramen-Order-App-UI-UX-Design'

    },

    {
        id: 3,
        user: 'Christina Morillo',
        job: 'Brand Manager',
        time:'2h',
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas accusamus cumque unde autem assumenda. Ullam et explicabo sit! Molestias delectus alias magni exercitationem similique iure quia tenetur? Mollitia porro dolores itaque in officia culpa pariatur, quasi iusto',
        likes: '1244',
        comments : '62',
        userImage : 'https://images.pexels.com/photos/1181686/pexels-photo-1181686.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
        postImages : [
            {
                id:1,
                url :'https://mir-s3-cdn-cf.behance.net/project_modules/1400/36bbbc137792503.62115d2d46e05.png'
            }, 
            {
                id:2,
                url :'https://mir-s3-cdn-cf.behance.net/project_modules/1400/abc180137792503.62115d2d4667c.jpg'
            }, 
            {
                id:3,
                url :'https://mir-s3-cdn-cf.behance.net/project_modules/1400/17cdec137792503.62115d2d49e1c.jpg'
            }, 
        ],
        link: 'https://www.behance.net/gallery/137792503/OSAKA-FOOD-Brand-Identity'
    },
])

</script>

<style lang="scss" scoped>

</style>