<template>
  <section class="border-b border-line px-8 pb-20 pt-24">
    <div class="mx-auto max-w-[1080px]">
      <div class="mb-5 flex items-center gap-2 font-mono text-[13px] text-accent">
        <span class="h-[7px] w-[7px] animate-pulse rounded-full bg-accent" />
        disponível para novos projetos
      </div>

      <h1 class="max-w-3xl font-sans text-[clamp(40px,6vw,68px)] font-semibold leading-[1.05] tracking-tight">
        Eu construo software que <span class="text-accent">funciona</span>, é rápido e resolve
        problemas reais.
      </h1>

      <p class="mt-6 max-w-lg text-lg leading-relaxed text-ink-soft">
        Sou desenvolvedor(a) e este é o lugar onde reúno o que já construí — do primeiro commit ao
        deploy. Dê uma olhada nos projetos abaixo.
      </p>

      <div class="mt-9 flex flex-wrap gap-3">
        <a
          href="#projetos"
          class="inline-flex items-center gap-2 rounded-md bg-ink px-5 py-3 font-mono text-sm text-bg transition-transform hover:-translate-y-0.5"
        >
          Ver projetos ↓
        </a>
        <a
          href="https://github.com/seu-usuario"
          target="_blank"
          rel="noopener"
          class="inline-flex items-center gap-2 rounded-md border border-line px-5 py-3 font-mono text-sm transition-all hover:-translate-y-0.5 hover:border-ink"
        >
          GitHub ↗
        </a>
      </div>
    </div>
  </section>
</template>
