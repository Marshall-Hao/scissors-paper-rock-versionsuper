<template>
    <Banner />
    <div class="justify-self-center flex space-x-10 mt-14 items-center">
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