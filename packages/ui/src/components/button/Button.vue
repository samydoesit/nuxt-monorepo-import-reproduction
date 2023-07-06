<script lang="ts" setup>
import type { ButtonIconSize, ButtonType } from './Button.model'
import { ButtonIconSizes, ButtonTypes } from './Button.model'

withDefaults(defineProps<{
  prefix: string
  type?: ButtonType
  iconSize?: ButtonIconSize
  loading?: boolean
  disabled?: boolean
}>(), {
  type: () => ButtonTypes.Primary,
  iconSize: () => ButtonIconSizes.Normal,
  loading: false,
  disabled: false,
})

defineEmits<{
  (e: 'click'): void
}>()
</script>

<template>
  <button @click="$emit('click')">
      <slot>Button Text</slot>
  </button>
</template>
