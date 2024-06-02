<script>
import products from '../assets/data/db.json';
import ProductElement from "./ProductElement.vue"
export default {
    name: "ProductsList",
    data() {
        return {
            products: products.products,
        }
    },
    components: {
        ProductElement
    }
}
</script>

<template>
    <div class="container" id="container">
        <div class="row">
            <ProductElement v-for="(product, i) in products" :key="product.id" :firstImage="product.frontImage"
                :secondImage="product.backImage" :brand="product.brand" :title="product.name" :price="product.price"
                :heart="product.isInFavorites" :badges="product.badges" :id="product.id" />
        </div>
    </div>
</template>

