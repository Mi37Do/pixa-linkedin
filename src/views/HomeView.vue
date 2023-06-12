<script setup>
import ProfileSide from '../components/main/profileSide.vue';
import postsMiddle from '../components/main/postsMiddle.vue';
import TopBar from '../components/topBar.vue';
import NewPostButton from '../components/main/newPostButton.vue';
import LeftSide from '../components/main/leftSide.vue';
import { ref } from 'vue';
import AngleDown from '../assets/icons/angleDown.vue';
import SearchIcon from '../assets/icons/searchIcon.vue';
import NewPostModal from '../components/main/newPostModal.vue';


const contacts = ref(false)

const messeges = ref([
  {
    id: 1,
    user : 'Elen Yakova',
    userImage : 'https://images.pexels.com/photos/91227/pexels-photo-91227.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
    messages : 2,
    status : 'connected',
    reply : null
  },
  {
    id: 2,
    user : 'Sara Sushi',
    userImage : 'https://images.pexels.com/photos/871495/pexels-photo-871495.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
    messages : 0,
    status : 'away',
    reply : 'so cool, lets do it'
  },
  {
    id: 1,
    user : 'Christina Morillo',
    userImage : 'https://images.pexels.com/photos/1181686/pexels-photo-1181686.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
    messages : 4,
    status : 'disconnected',
    reply : null
  },
])

</script>

<template>

  <div class="w-full h-screen flex lg:hidden flex-col items-center justify-center gap-4 text-lg font-semibold">
    <span>Available on pc device only</span>
    <span>Visit my portfolio : <a href="https://pixaviz.vercel.app/" class="text-primary">pixaviz.</a></span>

    <span class="loading loading-ring loading-md"></span>
  </div>

  <main class="w-full h-screen bg-slate-100 hidden lg:flex justify-center">
    <NewPostModal/>
    <div class="w-full h-full max-w-screen-xl flex flex-col">
      <TopBar/>
      <div class="w-full grow px-8 overflow-hidden">
        <div class="w-full h-full flex gap-4">
          <div class="w-72 2xl:w-80w-80 h-full flex-none relative">
            <ProfileSide/>
          </div>
          
          <div class="grow h-full relative">
            <postsMiddle/>

            <NewPostButton/>
            
          </div>
          <div class="w-72 2xl:w-80w-80 h-full flex-none relative">
            <LeftSide/>

            <div class="w-72 2xl:w-80 h-fit fixed z-20 bottom-0 rounded-t-lg pl-4 flex flex-col gap-0">
              <button @click="contacts = !contacts" class="w-full h-12 bg-white rounded-t-lg border border-l-slate-200 flex items-center justify-between p-2">
                <div class="flex gap-4 items-center">
                  <img src="@/assets/me.png" class="w-8 h-8 rounded" alt="">
                  <span class="capitalize font-semibold">messenger</span>
                </div>

                <AngleDown class="w-5 h-5 mr-2 mt-1 fill-slate-500 transition-all duration-200 delay-150" :class="contacts ? 'rotate-180' : 'rotate-0'"/>
                
              </button>
              <div class="w-full bg-white border-x border-slate-200 shadow-xl shadow-primary/10 transition-all duration-200 p-2" :class="contacts ? 'h-[70vh]' : 'h-0 delay-200'">
              <div class="w-full h-full flex flex-col gap-2">

                <div class="w-full h-fit flex items-center relative">
                  <SearchIcon class="w-4 h-4 left-2 absolute fill-slate-400 top-5"/>
                 <input v-model="searchInput" type="text" placeholder="search" class="block w-full h-10 rounded-md border-0 py-1.5 pr-4 pl-8 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-1 focus:ring-inset focus:ring-primary text-sm sm:leading-6 bg-white mt-2">
                </div>
                

                <div class="w-full flex flex-col gap-4">
                  <div v-for="i in messeges" :key="i.id" class="w-full flex gap-2 py-2 border-b border-slate-100 relative cursor-pointer">
                    
                    <div class="w-10 h-10 relative flex-none">
                      <img :src="i.userImage" class="w-10 h-10 rounded-md object-cover" alt="">
                      <span class="w-4 h-4 rounded-full absolute border-2 border-white -bottom-1 -right-1" :class="i.status === 'connected' ? 'bg-green-500' : i.status === 'away' ? 'bg-amber-500' : 'bg-slate-400'"></span>
                    </div>

                    <div class="grow flex h-10 flex-col overflow-hidden">
                      <span class="capitalize font-semibold">{{i.user}}</span>
                      <span v-if="!i.reply" class="turncate text-slate-400">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Pariatur, illum!</span>
                      <span v-else class="turncate text-slate-400">you : {{ i.reply }}</span>
                    </div>

                    <span v-if="i.messages !== 0" class="w-4 h-4 bg-primary rounded-full text-white text-xs my-auto flex items-center justify-center font-semibold absolute right-0">{{i.messages}}</span>
                    
                  </div>
                </div>
              </div>
            </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
