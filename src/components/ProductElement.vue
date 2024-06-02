<script>
export default {
    name: "ProductElement",
    props: {
        id: "Number",
        firstImage: "String",
        secondImage: "String",
        brand: "String",
        title: "String",
        price: "Number",
        heart: "Boolean",
        badges: "Array"
    },
    methods: {
        findBadge(badgeType) {
            return this.badges.find(badge => badge.type === badgeType)
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
    <div class="col-33">
        <div class="content">
            <img :src="`/img/${firstImage}`" class="main-image" alt="img">
            <img :src="`/img/${secondImage}`" class="hidden-image" alt="imgb">
            <div class="heart" v-if="heart">&hearts;</div>
            <div class="heart empty" v-else>&#9825;</div>
            <div v-if="findBadge('discount')" class="label discount"> {{
                findBadge('discount').value }} </div>
            <div v-if="findBadge('tag')" class="label sustainability" :class="{ img6: id === 6 }">
                {{ findBadge('tag').value }}</div>
        </div>
        <div class="caption">
            <p class="brand"> {{ brand }} </p>
            <h3> {{ title }} </h3>
            <span v-if="findBadge('discount')" class="new-price">{{
                newPrice(findBadge('discount').value, price) }}
                &euro;</span>
            <span class="new-price" v-else> {{ price }} </span>
            <span v-show="findBadge('discount')" class="old-price">{{
                price }} &euro;</span>
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

.heart.empty {
    color: black;
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