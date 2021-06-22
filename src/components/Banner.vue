<template>
    <div class="p-5 mt-10 border-2 border-white justify-self-center rounded-xl w-3/6 border-opacity-90 flex justify-between">
        <img src="../assets/images/logo-bonus.svg" alt="">
        <div class="bg-white py-3 px-8 rounded-xl text-center">
            <p class="text-lg font-semibold text-blue-800 tracking-wider font-mono">SCORE</p>
            <p class="text-6xl font-bold text-gray-800 tracking-tighter ">12</p>
        </div>
    </div>
</template>

<script>
import { ref } from '@vue/reactivity'
export default {
    setup() {
        const score = ref('')
    }
}
</script>
