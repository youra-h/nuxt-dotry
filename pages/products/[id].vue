<template lang="">
    <product-details :product="product" />
</template>

<script setup>
definePageMeta({
    layout: 'products',
})

const { id } = useRoute().params

const { data: product } = await useFetch(`https://fakestoreapi.com/products/${id}`, { key: id })

if (!product.value) {
    throw createError({ statusCode: 404, message: 'Product not found', fatal: true })
}
</script>

<style lang="">

</style>