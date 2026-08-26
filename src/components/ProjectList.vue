<script setup>
import { projects } from '../data/projects'
import ProjectCard from './ProjectCard.vue'
</script>

<template>
  <section id="projetos" class="border-b border-line px-8 py-20">
    <div class="mx-auto max-w-[1080px]">
      <div class="mb-10 flex flex-wrap items-baseline justify-between gap-3">
        <h2 class="font-sans text-[28px] font-semibold tracking-tight">Projetos</h2>
        <span class="font-mono text-[13px] text-ink-soft">~/projetos</span>
      </div>

      <div class="flex flex-col">
        <ProjectCard v-for="project in projects" :key="project.slug" :project="project" />
      </div>

      <div class="mt-6 rounded-lg border border-dashed border-line px-4 py-3.5 font-mono text-xs text-ink-soft">
        // edite <code>src/data/projects.js</code> para trocar pelos seus projetos reais.
      </div>
    </div>
  </section>
</template>
