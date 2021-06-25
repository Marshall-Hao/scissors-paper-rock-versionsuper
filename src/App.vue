<template>
  <div class="grid relative px-10 bg-gradient-radial transform  from-blue-600 to-blue-900 h-screen w-screen bg-no-repeat">
    <router-view/>
    <Rules />  
  </div>
</template>

<script>
import Banner from './components/Banner.vue'
import Rules from './components/Rules.vue'

export default {
    components: { Banner, Rules}
}
</script>

<style>

</style>
