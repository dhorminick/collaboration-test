<template>
  <div class="min-h-screen flex justify-center pt-9">
    <div class="w-full max-w-md px-4">
      <h1 class="text-3xl font-semibold text-center mb-6">Sign in</h1>

      <form @submit.prevent="handleLogin" class="flex flex-col">
        <!-- EMAIL -->
        <Input
          label="Email"
          pc="Enter your email"
          type="email"
          id="email"
          v-model="loginData.email"
        />

        <!-- PASSWORD -->
        <Input 
          label="Password"
          pc="Enter your password"
          type="password"
          id="password"
          v-model="loginData.password"
        /> 

        <Button type="submit" buttonName="Login" />
      </form>

      <p class="text-center mt-4">
        Don't have an account? 
        <NuxtLink to="/auth/signup" class="text-button font-semibold hover:underline">
          Sign up
        </NuxtLink>
      </p>
    </div>
  </div>
</template>


<script setup>
import Input from '~/components/Input.vue';

const loginData = ref({
  email: '',
  password: ''
})

const handleLogin = async () => {
  try {
    const res = await $fetch('/api/auth/login', {
      method: 'POST',
      body: {...loginData.value}
    })
    alert('Logged in successfully!');
    navigateTo(res.redirect) // you will be returning a path from the backend called redirect
  } catch (error) {
    alert('could not Login try again');
  }
}
</script>

<style scoped>

</style>