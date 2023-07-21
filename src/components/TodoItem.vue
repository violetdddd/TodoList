<template>
    <div class="pt-1 flex flex-row gap-2">
        <h3 class="w-full p-2 rounded-lg border border-gray-400 text-xl text-gray-900"
        :class="{'bg-gray-500 text-gray-300':turnGray,' bg-yellow-50':!turnGray}">{{ msg }}</h3>
        <button @click="turnGray = !turnGray" class="flex-1 px-2 py-2 rounded-lg font-semibold text-md  focus:ring-2"
        :class="{'bg-gray-500 focus:ring-gray-400 text-gray-300' : turnGray,' bg-green-600  focus:ring-green-300 text-white hover:bg-green-700':!turnGray}">Done</button>
        <button @click="$emit('delete')" class="flex-1 px-2 py-2 rounded-lg font-semibold text-md text-white bg-rose-600 hover:bg-rose-700 focus:ring-2 focus:ring-rose-300">Delete</button>
    </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const turnGray=ref(false)

defineProps({
    msg:{
        type:String,
        required:true,
    }
})
defineEmits({
    delete:null,
})
</script>