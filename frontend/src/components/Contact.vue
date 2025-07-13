<template>
  <footer id="kontak" class="py-20 bg-gray-800 text-white">
    <div class="container mx-auto px-6 text-center">
      <SectionTitle title="" />
      <p class="text-xl text-gray-300 mb-8">Jangan ragu untuk terhubung atau bertanya.</p>
      <a
        href="mailto:emailanda@example.com"
        class="bg-blue-600 text-white font-bold py-3 px-6 rounded-lg hover:bg-blue-700 transition-colors duration-300 inline-block mb-12"
      >
        Kirim Email
      </a>
      <div class="flex justify-center space-x-6 mb-8">
        <a
          href="https://github.com/Rizall3003"
          target="_github"
          class="text-gray-400 hover:text-white transition-colors duration-300 text-2xl"
        >
          <i class="bi bi-github"></i>
        </a>
        <a
          href="https://www.linkedin.com/in/rizal-anggoro-a91535264"
          target="_blank"
          class="text-gray-400 hover:text-white transition-colors duration-300 text-2xl"
        >
          <i class="bi bi-linkedin"></i>
        </a>
        <a
          href="https://www.instagram.com/rzalnggr_"
          target="_blank"
          class="text-gray-400 hover:text-white transition-colors duration-300 text-2xl"
        >
          <i class="bi bi-instagram"></i>
        </a>
      </div>
      <p class="text-gray-500">
        &copy; {{ new Date().getFullYear() }} Rizal Anggoro. Dibuat dengan <i class="bi bi-heart-fill text-black"></i>
      </p>
    </div>
  </footer>
</template>

<script setup>
import SectionTitle from './SectionTitle.vue'
</script>
