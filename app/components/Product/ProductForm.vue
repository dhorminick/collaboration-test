<template>
  <div class='max-w-md mx-auto pt-10'>
  <header class="text-orange-600 text-3xl font-bold mb-8">CREATE PRODUCT PAGE</header>
    <Input v-model="create_form.name">Product Name</Input>
    <div class="mt-3 mb-3">
      <InputLabel>Product Description</InputLabel>
      <textarea rows="10" :class="inputStyle" v-model="create_form.desc"> </textarea>
    </div>
    <div class="mt-3 mb-3">
      <InputLabel>Product Category</InputLabel>
      <select :class="inputStyle" v-model="create_form.category">
      <option v-for="option,index in options" :key="index">{{ option }}</option>
      </select>
    </div>
    <Input input-type="number" v-model="create_form.price" >Product Price</Input>
  <Button class="mt-5" @click="submitForm">Add Product</Button>
  </div>
</template>

<script setup>
// import InputLabel from '../Input/InputLabel.vue';
const create_form = ref({
  name: '',
  desc: '',
  category:'',
  price: 0.0
})
const options = [
  'Fashion', 'Technology', 'Home items', 'Others'
]

function submitForm() {
  console.log('Submitted product:', create_form.value);
}
</script>

<style lang="scss" scoped></style>
