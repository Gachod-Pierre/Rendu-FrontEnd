<script setup lang="ts">
import MyButton from './MyButton.vue';
import MyInput from './MyInput.vue';
import { ref } from 'vue';

const email = ref('')
const password = ref('')

const postLogin = () => {
  console.log('Logging in with', email.value, password.value)
}

</script>

<template>
    <form @submit.prevent="postLogin">
        <MyInput label="Username" type="email" v-model="email"/>
        <MyInput label="Password" type="password" v-model="password"/>
        <MyButton type="submit">Se connecter</MyButton>
    </form>
</template>