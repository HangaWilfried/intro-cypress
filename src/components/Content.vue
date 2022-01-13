<template>
    <main class="flex flex-col items-center justify-center">
        <div class="flex gap-x-4 text-3xl font-medium capitalize">
            welcome <span class="text-blue-600">{{user}}</span>
        </div>
        <div class="flex w-full justify-center gap-x-5 mt-10">
          <button @click.prevent="user=''"
            class="active:bg-cyan-300 hover:bg-red-400 hover:text-white font-bold rounded-md py-2 px-10 bg-red-200 text-gray-700">delete</button>
          <button @click.prevent="$emit('goToEdit', true)"
            class="active:bg-zinc-300 rounded-md py-2 px-10 bg-zinc-200 hover:bg-zinc-400 hover:text-white text-gray-700 font-bold">edit</button>
        </div>
        <div class="text-sm text-zinc-900 mt-20 place-self-end">
            you can customize your text card like you want!
        </div>
    </main>
</template>

<script>
  export default {
      name: 'Content',
      emits: ['goToEdit'],
      props: {
        user: {
          default: 'edouard',
          type: String,
          require: true
        }
      },
    }
</script>
