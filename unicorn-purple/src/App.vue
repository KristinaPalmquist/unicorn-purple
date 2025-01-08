<script setup>
import ThemeToggle from './components/ThemeToggle.vue';
import DetailsSummary from './components/DetailsSummary.vue';
import DetailsAccordion from './components/DetailsAccordion.vue';
</script>

<template>
  <div id="content">
    <ThemeToggle />
    <DetailsSummary />
    <DetailsAccordion />
  </div>
</template>

<style scoped>
#content {
  margin: 0 auto;
  width: clamp(300px, 80vw, 1200px);
  min-height: 100vh;
}
</style>
