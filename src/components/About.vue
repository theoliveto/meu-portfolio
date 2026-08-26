<script setup>
import SkillRow from './SkillRow.vue'

const skills = [
  { label: 'Frontend', value: 'React, TypeScript' },
  { label: 'Backend', value: 'Node.js, Python' },
  { label: 'Dados', value: 'PostgreSQL, Redis' },
  { label: 'Infra', value: 'Docker, AWS' },
]
</script>

<template>
  <section id="sobre" class="border-b border-line px-8 py-20">
    <div class="mx-auto grid max-w-[1080px] grid-cols-1 gap-14 md:grid-cols-[1.1fr_0.9fr]">
      <div>
        <span class="mb-4 block font-mono text-[13px] text-ink-soft">~/sobre-mim</span>
        <p class="max-w-md leading-relaxed text-ink-soft">
          Escreva aqui um parágrafo curto sobre sua trajetória: como começou a programar, que tipo
          de problema mais gosta de resolver e o que te diferencia.
        </p>
        <p class="mt-4 max-w-md leading-relaxed text-ink-soft">
          Adicione um segundo parágrafo sobre o que você busca agora — freelas, vaga CLT, projetos
          open source — para deixar claro o próximo passo para quem está lendo.
        </p>
      </div>
      <div>
        <span class="mb-4 block font-mono text-[13px] text-ink-soft">stack</span>
        <div class="flex flex-col gap-2.5">
          <SkillRow v-for="s in skills" :key="s.label" :label="s.label" :value="s.value" />
        </div>
      </div>
    </div>
  </section>
</template>
