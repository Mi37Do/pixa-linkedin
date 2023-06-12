<template>
    <div class="w-full h-fit flex flex-col gap-4   bg-white rounded-xl outline-1 outline-slate-200 p-4">
                <div class="w-full h-10 flex gap-4 items-center cursor-pointer">
                    <img :src="post.userImage" class="w-10 h-10 object-cover rounded-md" alt="">
                    <div class="grow h-full flex flex-col">
                        <span class="capitalize font-semibold text-base">{{ post.user }}</span>
                        <span class="capitalize text-slate-400 text-xs w-full flex justify-between">{{post.job}} <span>{{post.time}}.</span></span>
                    </div>
                </div>

                <div class="w-full flex flex-col">
                    <span>Dear network,</span>
                    <span class="turncate">{{post.text}}  <span class="text-primary">...see more</span></span>
                </div>

                <a :href="post.link" class="w-full grid gap-2" :class="post.postImages.length > 1 ? 'grid-cols-2' : 'grid-cols-1'">
                  <img :src="post.postImages[0].url" class="w-full h-full object-cover" :class="post.postImages.length === 1 ? 'row-span-2' : 'row-span-1'" alt=""> 
                  <div v-if="post.postImages.length > 1" class="w-full grid grid-rows-2 gap-2">
                    <img :src="post.postImages[1].url" class="w-full h-full object-cover"> 
                    <img :src="post.postImages[2].url" class="w-full h-full object-cover"> 
                  </div>
                </a>

                

                <div class="w-full h-10 flex justify-between gap-2 mt-1">
                    <div class="flex gap-2">
                        
                        <ReactionButton :likes="post.likes"/>

                        <button @click="showComments = !showComments" class="btn btn-sm btn-costume px-2  btn-ghost hover:fill-primary hover:text-primary" :class="showComments ? 'text-primary fill-primary' : 'fill-slate-400 text-slate-400'">
                        <CommentIcon class="w-5 h-5"/>
                        <span class="font-semibold">{{post.comments}}</span>
                        </button>

                        <button class="btn btn-sm btn-costume w-10 p-0 fill-slate-400 btn-ghost hover:fill-primary">
                            <ShareIcon class="w-5 h-5"/>
                        </button>
                    </div>

                    <div class="flex gap-2">
                        <button class="btn btn-sm btn-costume fill-slate-400 btn-ghost hover:fill-primary w-10 p-0">
                            <MessageIcon class="w-5 h-5"/>
                        </button>

                        <button class="btn btn-sm btn-costume fill-slate-400 btn-ghost hover:fill-primary w-10 p-0">
                            <DotsIcon class="w-5 h-5"/>
                        </button>
                    </div>
                    
                </div>
                <div  v-auto-animate class="w-full h-fit flex-none pr-2 pb-2">
                    <div v-if="showComments" class="w-full flex flex-col gap-4 -pt-4 flex-none">
                        <commentSection :comment="comment" :author="comment.user === post.user ? true : false" v-for="comment in comments" :key="comment.id"/> 
                    </div>
                </div>
                
    </div>
</template>

<script setup>
import CommentIcon from '../../assets/icons/commentIcon.vue';
import ShareIcon from '../../assets/icons/shareIcon.vue';
import MessageIcon from '../../assets/icons/messageIcon.vue';
import DotsIcon from '../../assets/icons/dotsIcon.vue';
import ReactionButton from './reactionButton.vue';
import commentSection from './commentSection.vue';
import { ref } from 'vue';

const props = defineProps(['post'])

const showComments = ref(false)

const comments = ref([
    {
        id : 1,
        user: 'sara sushi',
        job: 'frontend developer',
        time:'44min',
        text: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Consequatur, voluptatem.',
        likes: '16',
        replies : '12',
        userImage : 'https://images.pexels.com/photos/871495/pexels-photo-871495.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
    },
    {
        id : 2,
        user: 'Christina Morillo',
        job: 'Brand Manager',
        time:'2h',
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas accusamus cumque unde autem assumenda. Ullam et explicabo sit! Molestias delectus alias magni exercitationem similique iure quia tenetur? Mollitia porro dolores itaque in officia culpa pariatur, quasi iusto',
        likes: '1244',
        replies : '62',
        userImage : 'https://images.pexels.com/photos/1181686/pexels-photo-1181686.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
        reply : {
            user: 'Elen Yakova',
            job: 'Graphic Designer',
            time:'20min',
            text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas accusamus cumque unde autem assumenda. Ullam et explicabo sit! Molestias delectus alias magni exercitationem similique iure quia tenetur? Mollitia porro dolores itaque in officia culpa pariatur, quasi iusto',
            likes: '124',
            comments : '26',
            userImage : 'https://images.pexels.com/photos/91227/pexels-photo-91227.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
        }
    }
])
</script>

<style lang="scss" scoped>

</style>