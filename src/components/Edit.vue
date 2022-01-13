<template>
    <div class="flex flex-col items-center justify-center">
        <input type="text" v-model="userName" placeholder="type something..."
               class="h-8 w-full border border-blue-500 rounded-md p-4 text-gray-400 text-base focus:border-4 focus:border-blue-400 focus:outline-none"/>
        <div class="flex w-full justify-center gap-x-5 mt-10">
          <button class="active:bg-zinc-300 hover:bg-zinc-400 hover:text-white font-bold rounded-md py-2 px-10 bg-zinc-200 text-gray-700" @click.prevent="$emit('goToHomeWithoutModifies', false)">cancel</button>
          <button class="active:bg-blue-300 rounded-md py-2 px-10 bg-blue-200 hover:bg-blue-400 hover:text-white text-gray-700 font-bold"
                  @click.prevent="$emit('goToHome', {userName: userName, isDisplayed: false})">save</button>
        </div>
    </div>
</template>

<script>
    import {ref} from 'vue'

    export default {
        name: 'Edit',
        emits: ['goToHome', 'goToHomeWithoutModifies'],
        setup(){
          const userName = ref('')
          return{userName}
        }
    }
</script>
