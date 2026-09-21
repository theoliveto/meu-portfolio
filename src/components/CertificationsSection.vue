<script setup>
    const certifications = [
        {
            title: 'AWS Certified Cloud Practitioner',
            issuer: 'Amazon Web Services',
            date: '2025',
            id: 'ABC123XYZ',
            url: 'https://www.credly.com/badges/seu-badge',
        },
        {
            title: 'Vue.js Developers Certification',
            issuer: 'Vue School',
            date: '2024',
            id: '',
            url: 'https://example.com/credencial',
        },
        {
            title: 'Fundamentos de Node.js',
            issuer: 'Alura',
            date: '2023',
            id: '',
            url: '',
        },
    ]
</script>

<template>
    <section id="certificacoes" class="border-b border-line px-8 py-20">
        <div class="mx-auto max-w-[1080px]">
            <div class="mb-3 font-mono text-[13px] text-accent">certificações</div>

            <h2 class="max-w-2xl font-sans text-[clamp(28px,4vw,40px)] font-semibold leading-[1.1] tracking-tight">
                Formação contínua, com <span class="text-accent">credenciais</span> que você pode conferir.
            </h2>

            <p class="mt-4 max-w-lg text-lg leading-relaxed text-ink-soft">
                Cursos e provas que concluí para manter o que sei atualizado. Quando há credencial pública,
                o card leva até ela.
            </p>

            <ul class="mt-10 grid gap-4 sm:grid-cols-2 lg:grid-cols-3">
                <li v-for="cert in certifications" :key="cert.title">
                    <component
                        :is="cert.url ? 'a' : 'div'"
                        :href="cert.url || undefined"
                        :target="cert.url ? '_blank' : undefined"
                        :rel="cert.url ? 'noopener noreferrer' : undefined"
                        class="group flex h-full flex-col justify-between gap-6 rounded-md border border-line p-5 transition-all"
                        :class="cert.url ? 'hover:-translate-y-0.5 hover:border-ink' : ''"
                    >
                        <div>
                            <div class="font-mono text-[13px] text-ink-soft">{{ cert.issuer }}</div>
                            <h3 class="mt-2 font-sans text-lg font-semibold leading-snug tracking-tight">
                                {{ cert.title }}
                            </h3>
                        </div>

                        <div class="flex items-center justify-between font-mono text-[13px] text-ink-soft">
                            <span>
                                {{ cert.date }}<template v-if="cert.id"> · {{ cert.id }}</template>
                            </span>
                            <span v-if="cert.url" class="text-accent transition-transform group-hover:translate-x-0.5">
                                ver ↗
                            </span>
                        </div>
                    </component>
                </li>
            </ul>
        </div>
    </section>
</template>