<script setup>
import axios from 'axios'
import { ref, onMounted } from 'vue'
import SectionTitle from './SectionTitle.vue'

const educationHistory = ref([])

onMounted(async () => {
  try {
    const response = await axios.get('/api/education')
    educationHistory.value = response.data
  } catch (error) {
    console.error(error)
  }
})
</script>

<template>
  <section
    id="pendidikan"
    class="py-20 bg-gray-50 dark:bg-gray-900 min-h-screen transition-colors duration-300 font-sans"
  >
    <div class="container mx-auto px-6">
      <SectionTitle title="PENDIDIKAN" />
      <div class="relative">
        <!-- Garis tengah (sembunyi di mobile) -->
        <div
          class="absolute h-full border-r-2 border-gray-300 dark:border-gray-600 hidden md:block"
          style="left: 50%"
        ></div>

        <!-- Loop data pendidikan -->
        <div
          v-for="(edu, index) in educationHistory"
          :key="edu.id"
          class="mb-10 flex flex-col md:flex-row items-center w-full"
        >
          <!-- Kiri (even index) -->
          <template v-if="index % 2 === 0">
            <div class="w-full md:w-1/2 md:pr-8 flex justify-center md:justify-end mb-6 md:mb-0">
              <div
                class="bg-white dark:bg-gray-800 rounded-xl shadow-lg p-6 hover:shadow-2xl transition duration-300 flex items-center gap-4 max-w-md"
              >
                <img :src="edu.logo" class="w-16 h-16 object-contain" />
                <div class="text-right md:text-right text-left">
                  <p class="text-sm font-semibold text-blue-600 mb-1">
                    {{ edu.period }}
                  </p>
                  <h3 class="text-2xl font-bold text-gray-800 dark:text-white mb-1">
                    {{ edu.institution }}
                  </h3>
                  <p class="text-gray-600 dark:text-gray-300">{{ edu.major }}</p>
                </div>
              </div>
            </div>
            <div class="hidden md:flex w-1/2 justify-start">
              <div class="w-4 h-4 bg-blue-600 rounded-full z-10"></div>
            </div>
          </template>

          <!-- Kanan (odd index) -->
          <template v-else>
            <div class="hidden md:flex w-1/2 justify-end">
              <div class="w-4 h-4 bg-blue-600 rounded-full z-10"></div>
            </div>
            <div class="w-full md:w-1/2 md:pl-8 flex justify-center md:justify-start">
              <div
                class="bg-white dark:bg-gray-800 rounded-xl shadow-lg p-6 hover:shadow-2xl transition duration-300 flex flex-row-reverse md:flex-row items-center gap-4 max-w-md"
              >
                <img :src="edu.logo" class="w-16 h-16 object-contain" />
                <div class="text-left">
                  <p class="text-sm font-semibold text-blue-600 mb-1">
                    {{ edu.period }}
                  </p>
                  <h3 class="text-2xl font-bold text-gray-800 dark:text-white mb-1">
                    {{ edu.institution }}
                  </h3>
                  <p class="text-gray-600 dark:text-gray-300">{{ edu.major }}</p>
                </div>
              </div>
            </div>
          </template>
        </div>
      </div>
    </div>
  </section>
</template>
