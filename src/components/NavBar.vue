<script setup>
import { useMobileMenu } from '../composables/useMobileMenu'

const { isOpen, toggle, close } = useMobileMenu()
</script>

<template>
  <header class="sticky top-0 z-20 border-b border-line bg-bg/85 backdrop-blur-sm">
    <div class="mx-auto flex h-[68px] max-w-[1080px] items-center justify-between px-8">
      <div class="font-mono text-[15px] font-semibold tracking-tight">
        seu<span class="text-accent">@</span>portfolio
      </div>

      <nav class="hidden gap-7 font-mono text-[13px] text-ink-soft md:flex">
        <a href="#projetos" class="transition-colors hover:text-ink">projetos</a>
        <a href="#sobre" class="transition-colors hover:text-ink">sobre</a>
        <a href="#contato" class="transition-colors hover:text-ink">contato</a>
      </nav>

      <a
        href="#contato"
        class="hidden rounded-md border border-ink px-4 py-2 font-mono text-[13px] transition-colors hover:bg-ink hover:text-bg md:inline-block"
      >
        Contato
      </a>

      <button
        @click="toggle"
        :aria-expanded="isOpen"
        aria-controls="nav-mobile"
        :aria-label="isOpen ? 'Fechar menu' : 'Abrir menu'"
        class="flex h-9 w-9 flex-col items-center justify-center gap-[5px] rounded-md border border-line md:hidden"
      >
        <span
          class="block h-[1.5px] w-4 bg-ink transition-transform"
          :class="isOpen && 'translate-y-[6.5px] rotate-45'"
        />
        <span
          class="block h-[1.5px] w-4 bg-ink transition-opacity"
          :class="isOpen && 'opacity-0'"
        />
        <span
          class="block h-[1.5px] w-4 bg-ink transition-transform"
          :class="isOpen && '-translate-y-[6.5px] -rotate-45'"
        />
      </button>
    </div>

    <nav
      v-if="isOpen"
      id="nav-mobile"
      class="flex flex-col border-t border-line bg-surface md:hidden"
    >
      <a @click="close" href="#projetos" class="border-b border-line px-8 py-4 font-mono text-sm">
        projetos
      </a>
      <a @click="close" href="#sobre" class="border-b border-line px-8 py-4 font-mono text-sm">
        sobre
      </a>
      <a @click="close" href="#contato" class="px-8 py-4 font-mono text-sm">
        contato
      </a>
    </nav>
  </header>
</template>
