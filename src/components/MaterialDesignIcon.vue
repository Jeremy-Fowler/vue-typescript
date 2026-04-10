<script setup lang="ts">
defineProps({
  icon: { type: String, required: true },
  spin: { type: Boolean, default: false },
  height: { type: Number, default: 1.5 },
  // TODO this sucks
  color: { type: String, default: 'dark' }
})
</script>


<template>
  <svg :class="{ spin }">
    <path :d="icon" :fill="`var(--bs-${color})`" />
  </svg>
</template>


<style scoped lang="scss">
svg {
  height: v-bind("height + 'rem'");
  aspect-ratio: 1/1;
}

.spin {
  animation: spin 1s linear infinite;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}
</style>
