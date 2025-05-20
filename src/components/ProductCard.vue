<template>
    <div class="product-card">
        <img :src="product.image" alt="product.name" />
        <h2> {{ product.name }}</h2>
        <p>{{ product.desc }}</p>
        <p class="price">{{ product.price }} р.</p>
        <button class="details-btn">Подробнее</button> 
    </div>
</template>

<script>
export default{
    name: 'ProductCard',
    props:{
        product: Object
    }
}
</script>

<style scoped>

</style>