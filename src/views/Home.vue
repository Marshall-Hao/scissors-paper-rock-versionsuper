<template>
<Banner />
<div class="justify-self-center mt-36 relative grid">
  <img src="../assets/images/bg-pentagon.svg" alt="pentagon" class="h-52 md:h-auto" >
  <SelectionsList />
</div>
</template>

<script>
import Banner from '../components/Banner.vue'
import SelectionsList from '../components/SelectionsList.vue'
export default {
  name: 'Home',
  components: {SelectionsList, Banner}
}
</script>

