<template>
    <div class="p-5 mt-10 border-2 border-white justify-self-center rounded-xl w-11/12 md:w-3/6 border-opacity-90 flex justify-between content-center">
        <img src="../assets/images/logo-bonus.svg" alt="logo" class="h-20 md:h-auto">
        <div class="bg-white h-20 md:h-auto p-2 md:p-3 px-6 md:px-12 rounded-xl text-center">
            <p class="text-sm md:text-lg font-semibold text-blue-800 tracking-wider font-mono">SCORE</p>
            <p class="text-xl md:text-6xl font-bold text-gray-800 tracking-tighter ">{{ score }}</p>
            <p @click="handleClick" class="text-xs uppercase text-blue-800 tracking-wider font-mono cursor-pointer">refresh</p>
        </div>
    </div>
</template>

<script>
import { ref } from '@vue/reactivity'
import {  onMounted, watch, watchEffect } from '@vue/runtime-core'
export default {
    setup() {
        const score = ref(0)
        const localScore = ref(localStorage.getItem('counte'))
     
        watchEffect (() => {
            score.value = localScore.value
        })

        watch(localScore, () => {
            score.value = localScore.value
        })

        setTimeout(() => {
            localScore.value = localStorage.getItem('counte')
        }, 630)

        const handleClick = () => {
            localStorage.setItem('counte', 0)
            localScore.value = localStorage.getItem('counte')
        }

        return {score, handleClick}
    }
}
</script>
