<template>
    <div :class="selection">
        <router-link :to="{name: 'Game', params: {select: selection}}">
            <div class="bg-white p-10 md:p-16 rounded-full">
                <img v-if="selection === 'scissors'" src="../assets/images/icon-scissors.svg" :alt="selection" :class="selectionin">
                <img v-if="selection === 'paper'" src="../assets/images/icon-paper.svg" :alt="selection" :class="selectionin">
                <img v-if="selection === 'rock'" src="../assets/images/icon-rock.svg" :alt="selection" :class="selectionin">
                <img v-if="selection === 'lizard'" src="../assets/images/icon-lizard.svg" :alt="selection" :class="selectionin">
                <img v-if="selection === 'spock'" src="../assets/images/icon-spock.svg" :alt="selection" :class="selectionin">
            </div>    
        </router-link>
    </div>

</template>

<script>
import { ref } from '@vue/reactivity'
export default {
    props: ['selection'],
    setup(props) {
        const selectionin = ref('')

        selectionin.value = `${props.selection}in`

    return {selectionin}
    }
}
</script>

<style>

</style>