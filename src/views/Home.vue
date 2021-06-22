<template>
<div class="justify-self-center mt-36 relative grid">
  <img src="../assets/images/bg-pentagon.svg" alt="pentagon">
  <SelectionsList />
</div>
</template>

<script>
import SelectionsList from '../components/SelectionsList.vue'
export default {
  name: 'Home',
  components: {SelectionsList,}
}
</script>

