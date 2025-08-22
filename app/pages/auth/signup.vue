<template>
  <div class="min-h-screen flex justify-center pt-8">
    <div class="w-full max-w-md px-4"> 
      <h1 class="text-3xl font-semibold text-center mb-6">Signup Page</h1>

      <form @submit.prevent="handleSignup" class="flex flex-col">
        <!-- NAME -->
        <Input 
          label="Name"
          pc="Enter your name"
          type="text"
          id="name"
          v-model="userData.name"
        />

        <!-- EMAIL -->
        <Input 
          label="Email"
          pc="Enter your email"
          type="email"
          id="email"
          v-model="userData.email"
        />

        <!-- PASSWORD -->
        <Input 
          label="Password"
          pc="Create your password"
          type="password"
          id="password"
          v-model="userData.password"
        /> 

        <Button type="submit" buttonName="Signup" />
      </form>
      <p class="text-center mt-4">
        Already have an account? 
        <NuxtLink to="/auth/login" class="text-button font-semibold hover:underline">
          Sign in
        </NuxtLink>
      </p>
    </div>
  </div>
</template>


<script setup>
import Input from '~/components/Input.vue';

const userData = ref({
  name: '',
  email: '',
  password: ''
})

const handleSignup = async () => {
  try {
    const res = await $fetch('/api/auth/signup', {
      method: 'POST',
      body: {...userData.value}
    })
    alert('account created successfully!');
    navigateTo(res.redirect)
  } catch (error) {
    alert('could not sign up try again');
  }
}

</script>

<style scoped>

</style>
