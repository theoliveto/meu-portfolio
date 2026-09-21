<script setup>
import SkillRow from './SkillRow.vue'

const skills = [
  { label: 'Frontend', value: 'Vue (Vuetify), React, TS, JS, tailwindcss' },
  { label: 'Backend', value: 'C# (.NET), Node.js, PHP (Laravel)' },
  { label: 'Dados', value: 'SQL Server, PostgreSQL & mySQL' },
  { label: 'Infra', value: 'Docker, AWS' },
  { label: 'Tools', value: 'Git, GitHub, Visual Studio, VS Code, Insomnia' },
  { label: 'APIs', value: 'REST, JWT, Axios, GraphQL' },
  { label: 'Práticas', value: 'MVC, Clean Code, DTOs, Repositories' },
]
</script>

<template>
  <section id="sobre" class="border-b border-line px-8 py-20">
    <div class="mx-auto grid max-w-[1080px] grid-cols-1 gap-14 md:grid-cols-[1.1fr_0.9fr]">
      <div>
        <span class="mb-4 block font-mono text-[13px] text-ink-soft">~/sobre-mim</span>
        <p class="max-w-md leading-relaxed text-ink-soft">
          Desenvolvedor com formação em Análise e Desenvolvimento de Sistemas e experiência em aplicações desktop e web com C#, .NET, ASP.NET, Node.js, VB6 e SQL Server. Atuo na criação de APIs REST e integrações com E-commerce, assinatura eletrônica e órgãos ambientais, desenvolvendo soluções para o setor de gestão de resíduos.
        </p>

        <p class="mt-4 max-w-md leading-relaxed text-ink-soft">
          Busco oportunidades CLT, freelancer e projetos de desenvolvimento, onde possa aplicar meus conhecimentos, contribuir com soluções eficientes e evoluir continuamente em ambientes que valorizem qualidade, colaboração e inovação.
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
