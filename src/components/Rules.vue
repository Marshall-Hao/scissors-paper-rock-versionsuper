<template>
        <div v-if="showRules" class="justify-self-center bg-white h-full md:h-auto w-screen md:w-auto md:rounded-xl px-5 pt-8 pb-14 absolute top-0 md:top-40 flex flex-col justify-around">
            <div class="self-center md:self-auto md:flex md:justify-between">
                <p class="text-2xl font-bold font-mono text-gray-800 tracking-tighter">RULES</p>
                <img @click="showRules= false" src="../assets/images/icon-close.svg" alt="close" class="object-contain cursor-pointer opacity-80 hover:opacity-100 invisible md:visible" >
            </div>
            <div class="self-center grid justify-items-center space-y-6">
                <img src="../assets/images/image-rules-bonus.svg" alt="rules">
                <div class="text-lg md:text-sm font-bold font-mono text-gray-800 leading-relaxed">
                    <p class="tracking-wider">You Win: Score add 1 point</p>
                    <p class="tracking-tight">You Tied: Score minus 1 point</p>
                    <p class="tracking-tight">You Lose: Score minus 1 point</p>
                </div>
            </div>
            <img @click="showRules= false" src="../assets/images/icon-close.svg" alt="close" class="self-center object-contain cursor-pointer opacity-80 hover:opacity-100 visible md:invisible" >
        </div>

        <div class="justify-self-center md:justify-self-end mb-32 md:mb-48 mt-28 md:mt-12">
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