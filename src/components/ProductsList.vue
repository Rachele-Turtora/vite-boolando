<script>
export default {
    name: "ProductsList",
    data() {
        return {
            cards: [
                {
                    mainImg: "../../img/1.webp",
                    hiddenImg: "../../img/1b.webp",
                    discount: "-50%",
                    sustainability: true,
                    brand: "Levi's",
                    description: "relaxed fit tee unisex",
                    newPrice: "14,99",
                    oldPrice: "29,99"
                },
                {
                    mainImg: "../../img/2.webp",
                    hiddenImg: "../../img/2b.webp",
                    discount: "-30%",
                    sustainability: false,
                    brand: "Guess",
                    description: "roses tee",
                    newPrice: "20,99",
                    oldPrice: "29,99"
                },
                {
                    mainImg: "../../img/3.webp",
                    hiddenImg: "../../img/3b.webp",
                    discount: "-30%",
                    sustainability: false,
                    brand: "Come Zucchero Filato",
                    description: "voglia di colori pastello",
                    newPrice: "129,99",
                    oldPrice: "184,99"
                },
                {
                    mainImg: "../../img/4.webp",
                    hiddenImg: "../../img/4b.webp",
                    discount: "-50%",
                    sustainability: true,
                    brand: "Levi's",
                    description: "tee unisex",
                    newPrice: "14,99",
                    oldPrice: "29,99"
                },
                {
                    mainImg: "../../img/5.webp",
                    hiddenImg: "../../img/5b.webp",
                    discount: false,
                    sustainability: false,
                    brand: "Maya Deluxe",
                    description: "stripe bodice",
                    newPrice: "99,99",
                    oldPrice: null
                },
                {
                    mainImg: "../../img/6.webp",
                    hiddenImg: "../../img/6b.webp",
                    discount: false,
                    sustainability: true,
                    brand: "Esprit",
                    description: "maglione - black",
                    newPrice: "29,99",
                    oldPrice: null
                }
            ]
        }
    }
}
</script>

<template>
    <div class="container" id="container">
        <div class="row">
            <div class="col-33" v-for="(card, i) in  cards ">
                <div class="content">
                    <img :src="card.mainImg" class="main-image" alt="img1">
                    <img :src="card.hiddenImg" class="hidden-image" alt="img1b">
                    <div class="heart">&hearts;</div>
                    <div v-show="card.discount" class="label discount"> {{ card.discount }} </div>
                    <div v-show="card.sustainability" class="label sustainability"
                        :class="{ img6: i === cards.length - 1 }">
                        Sostenibilità</div>
                </div>
                <div class="caption">
                    <p class="brand"> {{ card.brand }} </p>
                    <h3> {{ card.description }} </h3>
                    <span class="new-price">{{ card.newPrice }} &euro;</span>
                    <span v-show="card.discount" class="old-price">{{ card.oldPrice }} &euro;</span>
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

    &:hover {
        color: red;
    }
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