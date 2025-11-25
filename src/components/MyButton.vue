<script setup lang="ts">

const props = defineProps<{
  size?: 'giant' | 'large' | 'medium' | 'small' | 'tiny'
  disabled?: boolean
  href?: string
}>()

</script>


<template>
  <component
  :is="href ? 'a' : 'button'"
  :href="href"
  class="button"
  :disabled="disabled"
>
  <slot />
</component>
</template>

<style scoped lang="scss">
.button {}
</style>
