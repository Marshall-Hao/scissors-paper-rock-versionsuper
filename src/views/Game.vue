<template>
    <Banner />
    <div class="justify-self-center flex flex-wrap md:space-x-10 mt-28 md:mt-14 items-center justify-center">
        <Combat />
    </div>
</template>

<script>
import Banner from '../components/Banner.vue'
import Combat from '../components/Combat.vue'

export default {
    components: {Combat, Banner}
}
</script>

<style>

</style>