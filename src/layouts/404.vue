<script setup lang="ts">
const router = useRouter()
const { t } = useI18n()
</script>

<template>
  <main class="px-4 py-10 text-center text-teal-700 dark:text-gray-200">
    <div class="text-4xl">
      <i-carbon-warning class="inline-block" />
    </div>
    <RouterView />
    <div>
      <button class="m-3 mt-8 text-sm" @click="router.back()">
        {{ t('button.back') }}
      </button>
    </div>
  </main>
</template>
