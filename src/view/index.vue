<template>
  <div class="container-fluid p-0">
    <!-- Header -->
    <!-- Main -->
    <div class="accordion " id="accordion">
      <GameCard></GameCard>

    </div>
    <!-- Main end-->
    <!-- Footer -->
  </div>
</template>

<script>
import GameCard from '../components/index/GameCard.vue';
  export default {
    data() {
      return {}
    },
    components: {
        GameCard
    },
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
