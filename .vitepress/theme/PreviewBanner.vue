<script setup lang="ts">
const isPreview = import.meta.env.VITE_DOCS_PREVIEW === 'true'
const prNumber = import.meta.env.VITE_DOCS_PREVIEW_PR
</script>

<template>
  <div v-if="isPreview" class="preview-banner">
    ⚠ <a :href="`https://github.com/dmocnik/test-docs/pull/${ prNumber }`">PR #{{ prNumber }}</a> Preview — This is not the production documentation
  </div>
</template>

<style scoped>
.preview-banner {
  position: fixed;
  left: 50%;
  bottom: 20px;
  transform: translateX(-50%);

  z-index: 100;

  padding: 8px 16px;
  border-radius: 8px;

  background: var(--vp-c-warning-soft);
  border: 1px solid var(--vp-c-warning-1);
  color: var(--vp-c-warning-1);

  font-size: 14px;
  font-weight: 600;

  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.15);
}
</style>