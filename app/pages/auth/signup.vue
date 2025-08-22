<template>
  <div class="min-h-screen flex flex-col items-center"> 
    <form @submit.prevent="handleSignup" class="bg-white shadow-md">
      <h1 class="text-2xl font-semibold">signup page</h1>
      <!-- NAME -->
      <div>
        <Input 
        label="Name"
        pc="Enter your name"
        type="text"
        id="name"
        v-model="userData.name"
         />
      </div>

      <!-- EMAIL -->
      <div>
        <Input 
        label="Email"
        pc="Enter your email"
        type="email"
        id="email"
        v-model="userData.email"
        
         />
      </div>

      <!-- PASSWORD -->
      <div>
        <Input 
        label="Password"
        pc="Enter your password"
        type="password"
        id="password"
        v-model="userData.password"
        
         />
      </div> 

      <Button type="submit" buttonName="submit" />
    </form>
  </div>
</template>

<script setup>
import Input from '~/components/Input.vue';

userData = ref({
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
    alert('account crreated successfully!');
    navigateTo(res.redirect)
  } catch (error) {
    alert('could not sign up try again');
  }
}

</script>

<style scoped>

</style>
