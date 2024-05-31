<script>
import IconsFooter from './IconsFooter.vue';

export default {
    name: "Footer",
    components: {
        IconsFooter
    }
}
</script>

<template>
    <footer>
        <div class="container">
            <div class="row">
                <div class="col-85">
                    <h4>Boolando S.r.l.</h4>
                    <div class="footer-list">
                        <ul>
                            <li>Informazioni legali</li>
                            <li>Informazioni sulla privacy</li>
                            <li>Diritto di recesso</li>
                        </ul>
                    </div>
                </div>
                <div class="col-15">
                    <IconsFooter />
                </div>
            </div>
        </div>
    </footer>
</template>

<style scoped lang="scss">
@use '../src/assets/styles/main' as *;

footer {
    background-color: $bg-footer;
    color: $cl-link;
    padding: 30px 0;
}

:deep(ul li) {
    font-size: 13px;
    padding-top: 10px;
    padding-right: 10px;
}
</style>