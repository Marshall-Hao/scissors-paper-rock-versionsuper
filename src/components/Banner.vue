<template>
    <div class="p-5 mt-10 border-2 border-white justify-self-center rounded-xl w-3/6 border-opacity-90 flex justify-between">
        <img src="../assets/images/logo-bonus.svg" alt="logo">
        <div class="bg-white py-3 px-12 rounded-xl text-center">
            <p class="text-lg font-semibold text-blue-800 tracking-wider font-mono">SCORE</p>
            <p class="text-6xl font-bold text-gray-800 tracking-tighter ">{{ score }}</p>
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
            console.log('watcheffect')
        })

        watch(localScore, () => {
            score.value = localScore.value
            console.log('watch')
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
