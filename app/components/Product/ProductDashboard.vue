
<template>
    <div class="max-w-5xl mx-auto pt-10">
        <header class="text-orange-600 text-3xl font-bold mb-8">DASHBOARD</header>
        <div class="flex gap-4 mb-8">
            <NuxtLink to="/create">
                <Button>Add Product</Button>
            </NuxtLink>
            <Button>Manage Product</Button>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
            <ProductCard
                v-for="(product, idx) in products"
                :key="idx"
                :name="product.name"
                :category="product.category"
                :price="product.price"
            />
        </div>
    </div>
</template>

<script setup>

const products = [
    { name: 'T-Shirt', category: 'Fashion', price: 19.99 },
    { name: 'Laptop', category: 'Technology', price: 899.99 },
    { name: 'Sofa', category: 'Home items', price: 499.99 },
    { name: 'Headphones', category: 'Technology', price: 59.99 },
    { name: 'Sneakers', category: 'Fashion', price: 79.99 },
    { name: 'Lamp', category: 'Home items', price: 29.99 },
]
</script>

<style lang="scss" scoped>
</style>