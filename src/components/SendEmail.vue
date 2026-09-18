<script setup lang="ts">
    import { reactive, ref } from 'vue'

    interface ContactForm {
        name: string
        email: string
        subject: string
        message: string
    }

    const form = reactive<ContactForm>({
        name: '',
        email: '',
        subject: '',
        message: '',
    })

    const status = ref<'idle' | 'sending' | 'success' | 'error'>('idle')
    const errorMessage = ref('')

    function validate(): boolean {
        if (!form.name.trim() || !form.email.trim() || !form.message.trim()) {
            errorMessage.value = 'Preencha nome, e-mail e mensagem.'
            return false
        }

        const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/

        if (!emailPattern.test(form.email)) {
            errorMessage.value = 'Informe um e-mail válido.'
            return false
        }

        errorMessage.value = ''
        return true
    }

    async function handleSubmit() {
        if (!validate()) {
            status.value = 'error'
            return
        }

        status.value = 'sending'

        try {
            const response = await fetch('https://formspree.io/f/xrpbbjrb', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(form),
            })

            if (!response.ok) throw new Error('Falha no envio')

            status.value = 'success'
            form.name = ''
            form.email = ''
            form.subject = ''
            form.message = ''
        } catch (err) {
            errorMessage.value = 'Não foi possível enviar agora. Tente novamente.'
            status.value = 'error'
        }
    }
</script>

<template>
    <section id="contato" class="bg-[#f7f6f3] text-neutral-900">
        <div class="mx-auto max-w-5xl px-6 py-20">
            <div class="flex items-baseline justify-between border-b border-neutral-200 pb-4">
                <h2 class="text-3xl font-bold tracking-tight">Contato</h2>
                <span class="font-mono text-sm text-neutral-400">~/contato</span>
            </div>

            <div class="mt-10 grid gap-12 md:grid-cols-5">

                <div class="md:col-span-2">
                    <p class="text-neutral-600">
                        Tem um projeto em mente ou só quer trocar uma ideia? Preencha o formulário ao lado — respondo o mais rápido possível.
                    </p>
                    <div class="mt-6 space-y-2 font-mono text-sm text-neutral-500">
                        <p><span class="text-blue-600">email</span> oliveto.vinicius@uceff.edu.br</p>
                        <p><span class="text-blue-600">local</span> Brasil</p>
                    </div>
                </div>

                <form class="md:col-span-3 space-y-5" @submit.prevent="handleSubmit">
                    <div class="grid gap-5 sm:grid-cols-2">
                        <div class="flex flex-col gap-2">
                            <label for="name" class="font-mono text-xs text-neutral-500">nome</label>
                            <input
                                id="name"
                                v-model="form.name"
                                type="text"
                                placeholder="Seu nome"
                                class="border border-neutral-300 bg-white px-4 py-2.5 text-sm outline-none transition-colors focus:border-blue-500"
                            />
                        </div>

                        <div class="flex flex-col gap-2">
                            <label for="email" class="font-mono text-xs text-neutral-500">e-mail</label>
                            <input
                                id="email"
                                v-model="form.email"
                                type="email"
                                placeholder="voce@exemplo.com"
                                class="border border-neutral-300 bg-white px-4 py-2.5 text-sm outline-none transition-colors focus:border-blue-500"
                            />
                        </div>
                        </div>
                        <div class="flex flex-col gap-2">
                            <label for="subject" class="font-mono text-xs text-neutral-500">assunto</label>
                            <input
                                id="subject"
                                v-model="form.subject"
                                type="text"
                                placeholder="Sobre o que você quer falar?"
                                class="border border-neutral-300 bg-white px-4 py-2.5 text-sm outline-none transition-colors focus:border-blue-500"
                            />
                        </div>

                        <div class="flex flex-col gap-2">
                            <label for="message" class="font-mono text-xs text-neutral-500">mensagem</label>
                            <textarea
                                id="message"
                                v-model="form.message"
                                rows="5"
                                placeholder="Conte um pouco sobre o projeto..."
                                class="resize-none border border-neutral-300 bg-white px-4 py-2.5 text-sm outline-none transition-colors focus:border-blue-500"
                            />
                        </div>

                        <div class="flex items-center gap-4 pt-2">
                            <button
                                type="submit"
                                :disabled="status === 'sending'"
                                class="bg-neutral-900 px-5 py-2.5 text-sm font-mono font-medium text-white transition-opacity hover:opacity-90 disabled:opacity-50"
                            >
                                {{ status === 'sending' ? 'Enviando...' : 'Enviar mensagem →' }}
                            </button>

                            <span v-if="status === 'success'" class="font-mono text-sm text-green-600">Mensagem enviada com sucesso.</span>

                            <span v-if="status === 'error'" class="font-mono text-sm text-red-600">{{ errorMessage }}</span>
                        </div>
                    
                </form>
            </div>
        </div>
    </section>
</template>