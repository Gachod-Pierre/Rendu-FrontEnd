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
  tiny: '-tiny',
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
  transition:
    background-color 0.15s,
    transform 0.15s,
    color 0.15s;

  --btn-bg: #3d4fff;
  --btn-color: #fff;
  --btn-bg-hover: #5b66ff;
  --btn-bg-press: #1e2bee;
  --btn-bg-disabled: #e6e6e6;
  --btn-color-disabled: #9f9f9f;

  background-color: var(--btn-bg);
  color: var(--btn-color);
}

&:hover:not([disabled]) {
  background-color: var(--btn-bg-hover);
}

&:active:not([disabled]) {
  background-color: var(--btn-bg-press);
  transform: scale(0.97);
}

&:focus-visible:not([disabled]) {
  outline: 3px solid rgba(50, 90, 255, 0.4);
  outline-offset: 2px;
}

&[disabled] {
  background-color: var(--btn-bg-disabled);
  color: var(--btn-color-disabled);
  cursor: not-allowed;
}

&.-giant {
  height: 64px;
  padding: 0 32px;
  font-size: 1.2rem;
}

&.-large {
  height: 56px;
  padding: 0 28px;
  font-size: 1.1rem;
}

&.-medium {
  height: 48px;
  padding: 0 24px;
  font-size: 1rem;
}

&.-small {
  height: 40px;
  padding: 0 20px;
  font-size: 0.9rem;
}

&.-tiny {
  height: 32px;
  padding: 0 16px;
  font-size: 0.8rem;
  border-radius: 6px;
}


</style>
