<template>
        <div v-if="showRules" class="justify-self-center bg-white rounded-xl p-5 absolute top-40">
            <div class="flex justify-between">
                <p class="text-2xl font-bold font-mono text-gray-800 tracking-tighter">RULES</p>
                <img @click="showRules= false" src="../assets/images/icon-close.svg" alt="close" class="object-contain cursor-pointer opacity-80 hover:opacity-100" >
            </div>
            <img src="../assets/images/image-rules-bonus.svg" alt="rules">
        </div>

        <div class="justify-self-end mb-10">
            <button @click="showRules = true" 
            class="px-10 py-2 rounded-2xl border border-white tracking-widest text-white text-md font-mono font-medium focus:outline-none hover:text-gray-200 hover:border-gray-200">
                RULES
            </button>
        </div>

</template>

<script>
import { ref } from '@vue/reactivity'
export default {
    setup() {
        const showRules = ref(false)

        return {showRules}
    }
}
</script>

<style>

</style>