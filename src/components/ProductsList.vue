<script>
import products from '../assets/data/db.json';
export default {
    name: "ProductsList",
    data() {
        return {
            products: products.products,
        }
    },
    methods: {
        findBadge(product, badgeType) {
            return product.badges.find(badge => badge.type === badgeType)
        },
        newPrice(discount, oldPrice) {
            const numDiscount = Number(discount.slice(1, 3))
            const newPrice = (oldPrice * (100 - numDiscount) / 100).toFixed(2)
            return newPrice
        }
    }
}
</script>

<template>
    <div class="container" id="container">
        <div class="row">
            <div class="col-33" v-for="(product, i) in products" :key="product.id">
                <div class="content">
                    <img :src="`/img/${product.frontImage}`" class="main-image" alt="img">
                    <img :src="`/img/${product.backImage}`" class="hidden-image" alt="imgb">
                    <div class="heart" v-if="product.isInFavorites">&hearts;</div>
                    <div v-if="findBadge(product, 'discount')" class="label discount"> {{
                        findBadge(product, 'discount').value }} </div>
                    <div v-if="findBadge(product, 'tag')" class="label sustainability"
                        :class="{ img6: i === products.length - 1 }">
                        {{ findBadge(product, 'tag').value }}</div>
                </div>
                <div class="caption">
                    <p class="brand"> {{ product.brand }} </p>
                    <h3> {{ product.name }} </h3>
                    <span v-if="findBadge(product, 'discount')" class="new-price">{{
                        newPrice(findBadge(product, 'discount').value, product.price) }}
                        &euro;</span>
                    <span class="new-price" v-else> {{ product.price }} </span>
                    <span v-show="findBadge(product, 'discount')" class="old-price">{{
                        product.price }} &euro;</span>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use '../src/assets/styles/main' as *;

.content {
    position: relative;
}

.heart {
    font-size: 30px;
    padding: 10px 15px;
    background-color: white;
    position: absolute;
    top: 10px;
    right: 0;
    color: red;
}

.discount {
    background-color: $cl-discount;
    left: 0;
}

.sustainability {
    background-color: $cl-sustainability;
    left: 60px;
}

.label {
    font-size: 15px;
    font-weight: 700;
    padding: 5px 10px;
    color: white;
    position: absolute;
    bottom: 50px;
}

h3 {
    text-transform: uppercase;
    font-size: 20px;
}

.new-price {
    color: red;
    font-size: 18px;
    font-weight: bolder;
}

.old-price {
    text-decoration: line-through;
    font-size: 18px;
    margin-left: 10px;
}

.img6 {
    left: 0;
}

.hidden-image,
.content:hover .main-image {
    display: none;
}

.content:hover .hidden-image {
    display: inline-block;
}
</style>