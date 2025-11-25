<script setup lang="ts">

const props = defineProps<{
  size?: 'giant' | 'large' | 'medium' | 'small' | 'tiny'
  disabled?: boolean
  href?: string
}>()

const sizeClass = {
  giant: '-giant',
  large: '-large',
  medium: '-medium',
  small: '-small',
  tiny: '-tiny'
}[props.size ?? 'medium']

</script>


<template>
  <component
  :is="href ? 'a' : 'button'"
  :href="href"
  class="button"
  :class="[sizeClass]"
  :disabled="disabled"
>
  <slot />
</component>
</template>

<style scoped lang="scss">
.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
  cursor: pointer;
  border: none;
  outline: none;
  border-radius: 8px;
  transition: background-color .15s, transform .15s, color .15s;
}
</style>
