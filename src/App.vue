<template>
  <Banner />
  <router-view/>
  <Rules />
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
