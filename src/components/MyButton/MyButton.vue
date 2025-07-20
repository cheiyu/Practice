<script setup>
import { computed, defineAsyncComponent } from 'vue'

const props = defineProps({
  onClick: {
    type: Function,
  },
  icon: {
    type: String,
    default: '',
  },
  theme: {
    type: String,
    default: 'primary',
  },
  size: {
    type: String,
    default: 'normal',
  },
  // isOutline: {
  //   type: Boolean,
  //   default: false,
  // },
  disabled: {
    type: Boolean,
    default: false,
  },
})

const iconComponent = computed(() => {
  if (!props.icon) return null
  return defineAsyncComponent(() => import(`@/assets/icons/${props.icon}.svg`))
})
</script>

<template>
  <div class="button-wrapper">
    <button
      class="button"
      :data-theme="theme"
      :data-size="size"
      :disabled="disabled"
      @click="props.onClick"
    >
      <slot />
      <div v-if="iconComponent" class="button-icon">
        <component :is="iconComponent" />
      </div>
    </button>
  </div>
</template>

<style scoped lang="scss">
@import './button';
</style>
