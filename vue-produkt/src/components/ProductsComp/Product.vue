<template>
    <div :class="['product', 'border']">
        <img :src="product.image" alt="image" class="image">
        <div :class="['product-info']">
            <h3>
                {{ product.title }} 

            </h3>
            <p>{{ product.description }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Product',
    props: {
        product: Object,
    },
}
</script>

<style scope>

.product {
    background: #f4f4f4;
    margin: 10px;
    padding: 10px 20px;
    cursor: pointer;
    display: flex;
    flex-direction: row;
}
.product-info {
    background: #f4f4f4;
    margin-left: 10px;
    text-align: left;
    display: flex;
    flex-direction: column;
}
.border{
   border: 5px solid black;
}

.image{
    width: 6vw;
    display: flex;
}

.product h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>