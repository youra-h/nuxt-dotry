<template lang="">
    <div class="card text-center">
        <img :src="product.image" :alt="product.title" class="w-full h-48 object-cover">
        <p class="font-bold text-gray-500 m-4 truncate">{{ product.title }}</p>        
        <!-- <p class="text-lg font-bold text-green-500">{{ product.price }}</p> -->
        <nuxt-link :to="`/products/${product.id}`">
            <p class="btn my-4">View details</p>
        </nuxt-link>
    </div>
</template>

<script setup>
const { product } = defineProps(['product'])
</script>

<style lang="">

</style>