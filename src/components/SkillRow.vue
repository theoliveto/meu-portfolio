<script setup>
defineProps({
  label: { type: String, required: true },
  value: { type: String, required: true },
})
</script>

<template>
  <div class="flex items-center justify-between rounded-md border border-line bg-surface px-3.5 py-2.5 font-mono text-[13px]">
    <span>{{ label }}</span>
    <span class="text-ink-soft">{{ value }}</span>
  </div>
</template>
