<template>
    <div class="grid justify-items-center">
        <span class="uppercase text-2xl tracking-wider font-mono font-bold text-white filter drop-shadow-lg mb-12">you picked</span>
        <div :class="selectedStyle">
            <div class="bg-white p-28 rounded-full grid">
                <img v-if="selected === 'scissors'" src="../assets/images/icon-scissors.svg" :alt="selected" class="transform scale-150 justify-self-center">
                <img v-if="selected === 'paper'" src="../assets/images/icon-paper.svg" :alt="selected" class="transform scale-150 justify-self-center">
                <img v-if="selected === 'rock'" src="../assets/images/icon-rock.svg" :alt="selected" class="transform scale-150 justify-self-center">
                <img v-if="selected === 'lizard'" src="../assets/images/icon-lizard.svg" :alt="selected" class="transform scale-150 justify-self-center">
                <img v-if="selected === 'spock'" src="../assets/images/icon-spock.svg" :alt="selected" class="transform scale-150 justify-self-center">
            </div>    
        </div>
    </div>

    <Result :userPick="selected" :housePick="housePicked" v-if="housePick"/>

    <div class="grid justify-items-center">
        <span class="uppercase text-2xl tracking-wider font-mono font-bold text-white filter drop-shadow-lg mb-12">The house picked</span>
        <div :class="housePickedStyle">
            <div class="p-28 rounded-full grid" :class="housePick ? 'bg-white' : 'bg-blue-800 bg-opacity-70'">
                <div v-if="!housePick" class="justify-self-center">
                    <div class="animate-spin h-14 w-14 rounded-full border-t-3 border-indigo-400 text-center text-indigo-400 font-xs font-bold uppercase"></div>
                </div>
                <img v-if="housePicked === 'scissors'" src="../assets/images/icon-scissors.svg" :alt="housePicked" class="transform scale-150 justify-self-center">
                <img v-if="housePicked === 'paper'" src="../assets/images/icon-paper.svg" :alt="housePicked" class="transform scale-150 justify-self-center">
                <img v-if="housePicked === 'rock'" src="../assets/images/icon-rock.svg" :alt="housePicked" class="transform scale-150 justify-self-center">
                <img v-if="housePicked === 'lizard'" src="../assets/images/icon-lizard.svg" :alt="housePicked" class="transform scale-150 justify-self-center">
                <img v-if="housePicked === 'spock'" src="../assets/images/icon-spock.svg" :alt="housePicked" class="transform scale-150 justify-self-center">
            </div>    
        </div>
    </div>
</template>

<script>
import Result from './Result.vue'
import { ref } from '@vue/reactivity'
import { useRoute } from 'vue-router'
import { onMounted } from '@vue/runtime-core'

export default {
    components: {Result},
    setup() {
        const route = useRoute()
        const housePick = ref(false)
        const selections = ref(['scissors', 'paper', 'spock', 'lizard', 'rock'])
        const housePicked = ref('')
        const housePickedStyle = ref('')

        const selected = route.params.select
        const selectedStyle = `${selected}-combat`

        onMounted(() => 
            setTimeout(() => {
                housePick.value = true 
                housePicked.value = selections.value[Math.floor(Math.random()*selections.value.length)]
                housePickedStyle.value = `${housePicked.value}-combat`
            }, 600)
        )

        return {selected, selectedStyle, housePicked, housePickedStyle, housePick}
    }
}
</script>

<style>

</style>