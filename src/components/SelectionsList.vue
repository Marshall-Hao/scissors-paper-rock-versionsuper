<template>
  <div v-for="selection in selections" :key="selection">
      <Selection :selection="selection" />
  </div>
</template>

<script>
import { ref } from '@vue/reactivity'
import Selection from './Selection.vue'
export default {
    components: {Selection},
    setup() {
        const selections = ref(['scissors', 'paper', 'spock', 'lizard', 'rock'])

        return {selections}
    }
}
</script>

<style>

</style>