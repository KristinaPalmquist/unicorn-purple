<script setup>
import { useDark, useToggle } from '@vueuse/core';

const isDark = useDark({
  selector: 'body', //element to add attribute to
  attribute: 'theme', // attribute name
  valueDark: 'custom-dark', // attribute value for dark mode
  valueLight: 'custom-light', // attribute value for light mode
});
const toggleDark = useToggle(isDark);
</script>

<template>
  <div id="theme-toggle">
    <button
      class="theme-toggle"
      type="button"
      @click="toggleDark()"
      aria-label="Toggle theme"
    >
      Toggle light/dark
    </button>
    <p>Dark Theme: {{ isDark }}</p>
  </div>
</template>

<style scoped>
#theme-toggle {
  margin: 2rem auto;
}
</style>
