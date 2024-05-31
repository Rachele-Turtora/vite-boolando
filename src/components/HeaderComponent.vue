<script>
import AppLogo from "./AppLogo.vue"
export default {
    name: "Header",
    components: {
        AppLogo
    },
    data() {
        return {
            listLink: ["Donna", "Uomo", "Bambini"],
            listIcon: ["fa-user-o", "fa-heart-o", "fa-shopping-bag"]
        }
    }
}
</script>

<template>
    <header>
        <div class="container">
            <div class="row">
                <div class="col-33">
                    <div class="header-list">
                        <ul>
                            <li v-for="link in listLink"><a href="#"> {{ link }} </a></li>
                        </ul>
                    </div>
                </div>
                <div class="col-33">
                    <AppLogo />
                </div>
                <div class="col-33 text-right">
                    <div class="header-list">
                        <ul>
                            <li v-for="icon in listIcon"><a href="#"><i :class="`fa ${icon}`" aria-hidden="true"></i></a>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<style scoped lang="scss">
@use '../src/assets/styles/main' as *;

header {
    position: fixed;
    width: 100%;
    background-color: $bg-header;
    z-index: 1;
    padding-top: 10px;
}

.text-right {
    text-align: right;
}

a {
    color: $cl-link;
}

li {
    font-size: 20px;
    padding: 0 10px;
}
</style>