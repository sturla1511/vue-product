<template>
    <Products :products="products"/>
</template>

<script>
 /*<Button 
        @btn-click="button()" 
        text="Button" 
    />*/
import Button from '../components/Button'
import Products from '../components/ProductsComp/Products'

export default {
    name: 'ProductsPage',
    props: {
        title: String,
    },
    components: {
        Products,
        Button,
    },
    data() {
        return {
            products: [],
        }
    }, 
    methods: {
        /*async button() {
            const res = await fetch('api/products')

            const data = await res.json()
            
            return data
        },*/

        async fetchProducts() {
            const res = await fetch('api/products')

            const data = await res.json()

            return data
        },
        async fetchProduct(id) {
            const res = await fetch(`api/products/${id}`)

            const data = await res.json()

            return data
        },
    },
    async created() {
        this.products = await this.fetchProducts()
    },
}
</script>