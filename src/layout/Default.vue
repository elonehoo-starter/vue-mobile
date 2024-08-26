<script setup lang="ts">
import { PHONE_RATIO } from '~/composables/constant'

const { width, height } = useWindowSize()

const isDesktop = computed(() => {
  return width.value > 500 && width.value / height.value > PHONE_RATIO
})

const caseWidth = computed(() => {
  return Math.min(
    width.value,
    isDesktop.value
      ? height.value * PHONE_RATIO - 5
      : width.value,
  )
})

const caseStyle = computed(() => ({
  width: `${caseWidth.value}px`,
}))
</script>

<template>
  <div
    class="box select-none m-0 h-100vh w-100vw bg-dark-400 font-mono font-thin text-[var(--theme-foreground)]"
  >
    <div
      id="phone-case"
      :style="caseStyle"
      class="bg-[var(--theme-background)] h-100vh overflow-y-auto overflow-x-hidden relative left-1/2 -translate-x-2/4 scrollbar-none [&::-webkit-scrollbar]:block [&::-webkit-scrollbar]:w-0px"
    >
      <slot />
    </div>
  </div>
</template>
