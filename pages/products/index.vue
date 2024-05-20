<template lang="">
    <div>
        <div class="grid grid-cols-4 gap-5">
            <div v-for="product in products" :key="product.id" class="bg-white shadow-md p-4">
                <product-card :product="product" />
            </div>
        </div>
    </div>
</template>

<script setup>
definePageMeta({
    layout: 'products',
})

// fetch the products from the API
const { data: products } = await useFetch('https://fakestoreapi.com/products')
</script>

<style lang="">

</style>