<template>
  <NConfigProvider :theme="theme" abstract :locale="zhCN" :date-locale="dateZhCN">
    <NMessageProvider>
      <NDialogProvider>
        <NLoadingBarProvider>
          <RouterView />
          <GlobalSetting />
        </NLoadingBarProvider>
      </NDialogProvider>
    </NMessageProvider>
  </NConfigProvider>
</template>

<script setup lang="ts">
import { RouterView } from 'vue-router'
import { storeToRefs } from 'pinia'
import {
  NConfigProvider,
  zhCN,
  dateZhCN,
  NMessageProvider,
  NDialogProvider,
  NLoadingBarProvider
} from 'naive-ui'
import { useThemeStore } from '@/stores/theme'
import GlobalSetting from '@@/core/GlobalSetting.vue'

const { theme } = storeToRefs(useThemeStore())
</script>
