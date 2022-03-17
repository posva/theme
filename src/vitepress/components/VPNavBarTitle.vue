<script lang="ts" setup>
import { useData } from 'vitepress'
import { Config } from '../config'
const { title, theme } = useData<Config>()
</script>

<template>
  <a class="VPNavBarTitle" href="/">
    <img
      v-if="theme.logo"
      :src="theme.logo"
      :alt="`${title} Logo`"
      class="logo"
    />
    <span class="text">{{ title }}</span>
  </a>
</template>

<style scoped>
.VPNavBarTitle {
  display: flex;
  align-items: center;
  padding-top: 1px;
  height: var(--vt-nav-height);
  transition: opacity 0.25s;
}

.VPNavBarTitle:hover {
  opacity: 0.6;
}

.logo {
  position: relative;
  width: 24px;
  height: 24px;
}

.logo + .text {
  padding-left: 8px;
}

.text {
  font-size: 16px;
  font-weight: 500;
}
</style>
