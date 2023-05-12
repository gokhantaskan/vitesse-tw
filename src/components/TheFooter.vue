<script setup lang="ts">
import { availableLocales, loadLanguageAsync } from '@/modules/i18n'

const { t, locale } = useI18n()

async function toggleLocales() {
  // change to some real logic
  const locales = availableLocales
  const newLocale = locales[(locales.indexOf(locale.value) + 1) % locales.length]
  await loadLanguageAsync(newLocale)
  locale.value = newLocale
}
</script>

<template>
  <nav class="flex justify-center gap-4 mt-6 text-xl">
    <RouterLink to="/" :title="t('button.home')">
      <i-carbon-campsite />
    </RouterLink>

    <button :title="t('button.toggle_dark')" @click="toggleDark()">
      <template v-if="!isDark">
        <i-carbon-sun />
      </template>
      <template v-else>
        <i-carbon-moon />
      </template>
    </button>

    <a :title="t('button.toggle_langs')" @click="toggleLocales()">
      <i-carbon-language />
    </a>

    <RouterLink to="/about" :title="t('button.about')">
      <i-carbon-dicom-overlay />
    </RouterLink>

    <a rel="noreferrer" href="https://github.com/antfu/vitesse" target="_blank" title="GitHub">
      <i-carbon-logo-github />
    </a>
  </nav>
</template>
