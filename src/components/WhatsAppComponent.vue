<script setup>
    import { computed } from 'vue'

    const props = defineProps({
        phone: { type: String, required: true },
        message: { type: String, default: 'Olá! Vim pelo seu site de portfólio e gostaria de mais informações.' },
    })

    const link = computed(
        () => `https://wa.me/${props.phone}?text=${encodeURIComponent(props.message)}`
    )
</script>

<template>
  <a
    :href="link"
    target="_blank"
    rel="noopener noreferrer"
    aria-label="Falar pelo WhatsApp"
    class="fixed bottom-5 right-5 z-50 flex h-14 w-14 items-center justify-center rounded-full bg-[#25D366] text-white shadow-lg transition-transform hover:scale-110 focus:outline-none focus-visible:ring-4 focus-visible:ring-green-300"
  >
    <svg viewBox="0 0 32 32" class="h-8 w-8 fill-current" aria-hidden="true">
      <path
        d="M16.003 3C9.374 3 4 8.373 4 15c0 2.116.553 4.18 1.6 6.003L4 29l8.152-1.57A11.94 11.94 0 0 0 16.003 27C22.63 27 28 21.627 28 15S22.63 3 16.003 3Zm0 21.8c-1.8 0-3.56-.484-5.1-1.4l-.366-.217-4.84.932.99-4.71-.238-.386A9.77 9.77 0 0 1 6.2 15c0-5.412 4.4-9.8 9.803-9.8 5.4 0 9.797 4.388 9.797 9.8 0 5.41-4.397 9.8-9.797 9.8Zm5.37-7.34c-.294-.147-1.742-.86-2.012-.958-.27-.098-.466-.147-.662.147-.196.294-.76.958-.932 1.155-.172.196-.343.22-.637.074-.294-.147-1.242-.458-2.366-1.46-.874-.78-1.464-1.743-1.636-2.037-.172-.294-.018-.453.13-.6.132-.132.294-.343.44-.515.148-.172.197-.294.295-.49.098-.197.05-.368-.024-.515-.074-.147-.662-1.595-.907-2.184-.24-.573-.482-.495-.662-.504l-.564-.01c-.196 0-.515.074-.785.368-.27.294-1.03 1.007-1.03 2.454 0 1.448 1.055 2.847 1.202 3.043.147.196 2.076 3.17 5.03 4.444.703.303 1.252.484 1.68.62.706.224 1.35.192 1.857.117.566-.085 1.742-.712 1.988-1.4.245-.687.245-1.276.172-1.4-.074-.122-.27-.196-.564-.343Z"
      />
    </svg>
  </a>
</template>