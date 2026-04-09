<script setup lang="ts">
defineProps({
  icon: { type: String, required: true },
  spin: { type: Boolean, default: false },
  height: { type: Number, default: 1.5 }
})
</script>


<template>
  <svg :class="{ spin }">
    <path :d="icon" />
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
