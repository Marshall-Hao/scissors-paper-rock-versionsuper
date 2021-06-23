<template>
    <div class="grid justify-items-center">
    <div v-if="userPick === housePick">
        <div class="text-6xl font-bold font-mono tracking-tight text-white drop-shadow-lg uppercase">
            <span class="mr-3">you</span>
            <span>tied</span>
        </div>
    </div>
   
    <div v-else>
        <div v-if="win">
            <div class="text-6xl font-bold font-mono tracking-tight text-white drop-shadow-lg uppercase">
                <span class="mr-6">you</span>
                <span>win</span>
            </div>
        </div>
        <div v-else>
            <div class="text-6xl font-bold font-mono tracking-tight text-white drop-shadow-lg uppercase">
                <span class="mr-2">you</span>
                <span>lose</span>
            </div>
        </div>
    </div>
    <button @click="handleClick" class="bg-white px-16 rounded-xl shadow-lg py-4 font-bold font-mono text-lg uppercase mt-5 text-blue-700">play again</button>
    </div>
</template>

<script>
import { ref } from '@vue/reactivity'
import { useRouter } from 'vue-router'
import { onMounted, onUpdated } from '@vue/runtime-core'

export default {
    props: ['userPick', 'housePick'],
    setup(props) {
        const win = ref(false)
        const router = useRouter()
        const counte = ref(0)
        const scissorsWin = ref(['paper', 'lizard'])
        const paperWin = ref(['rock', 'spock'])
        const rockWin = ref(['scissors', 'lizard'])
        const lizardWin = ref(['paper', 'spock'])
        const spockWin = ref(['rock', 'scissors'])
        

        const handleClick = () => {
            router.push({ name:'Home' })
        }

        counte.value = localStorage.getItem('counte')
        onMounted(() => {
            
            if ( props.userPick === 'scissors') {
                win.value = scissorsWin.value.includes(props.housePick)
            }
    
            if ( props.userPick === 'paper') {
                win.value = paperWin.value.includes(props.housePick)
            }
    
            if ( props.userPick === 'rock') {
                win.value = rockWin.value.includes(props.housePick)
            }
    
            if ( props.userPick === 'lizard') {
                win.value = lizardWin.value.includes(props.housePick)
            }
    
            if ( props.userPick === 'spock') {
                win.value = spockWin.value.includes(props.housePick)
            }
            
            if (win.value) {
                counte.value ++
            } else {
                counte.value -= 1
            }
            
            localStorage.setItem('counte', counte.value)
        })

        // counte.value = localStorage.getItem('counte')
        
        return { handleClick, win, counte }
    }
}
</script>

<style>

</style>