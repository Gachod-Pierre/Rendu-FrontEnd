<script setup lang="ts">
import MyButton from '@/components/MyButton.vue';
import MyLoginForm from '@/components/MyLoginForm.vue';

</script>

<template>
  <main>
    <h1>HP</h1>
    <MyButton @clickAndHover="() => console.log('Button clicked or hovered')"> Click or Hover me </MyButton>
    <MyLoginForm />
  </main>
</template>