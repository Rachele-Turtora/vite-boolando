<script>
export default {
    name: "Icons",
    data() {
        return {
            icons: ["fa-twitter", "fa-facebook-official", "fa-instagram", "fa-pinterest-square", "fa-youtube-play"]
        }
    }
}
</script>

<template>
    <h5>Trovaci anche su:</h5>
    <div class="footer-list">
        <ul>
            <li v-for="icon in icons"><i :class="`fa ${icon}`" aria-hidden="true"></i></li>
        </ul>
    </div>
</template>
