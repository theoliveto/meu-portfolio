<script setup>
defineProps({
  project: { type: Object, required: true },
})
</script>

<template>
  <a
    :href="project.url"
    target="_blank"
    rel="noopener"
    class="group block border-t border-line px-6 py-7 transition-all hover:bg-accent-soft hover:pl-8 last:border-b"
  >
    <div class="flex items-center justify-between gap-4">
      <div>
        <span class="mb-2 block font-mono text-[12.5px] text-accent">
          ~/projetos/{{ project.slug }}
        </span>
        <div class="font-sans text-xl font-semibold tracking-tight">{{ project.name }}</div>
      </div>
      <span
        class="flex-shrink-0 font-mono text-xl text-ink-soft transition-all group-hover:-translate-y-1 group-hover:translate-x-1 group-hover:text-accent"
      >
        ↗
      </span>
    </div>

    <p class="mt-2 max-w-xl text-[15px] leading-relaxed text-ink-soft">
      {{ project.description }}
    </p>

    <div class="mt-4 flex flex-wrap gap-2">
      <span
        v-for="tag in project.tags"
        :key="tag"
        class="rounded-md border border-line bg-surface px-2.5 py-1 font-mono text-[11.5px] text-ink-soft group-hover:border-accent/25 group-hover:bg-white"
      >
        {{ tag }}
      </span>
    </div>
  </a>
</template>
