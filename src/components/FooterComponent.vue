<script>
export default {
    name: "Footer"
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
                    <h5>Trovaci anche su:</h5>
                    <div class="footer-list">
                        <ul>
                            <li><i class="fa fa-twitter" aria-hidden="true"></i></li>
                            <li><i class="fa fa-facebook-official" aria-hidden="true"></i></li>
                            <li><i class="fa fa-instagram" aria-hidden="true"></i></li>
                            <li><i class="fa fa-pinterest-square" aria-hidden="true"></i></li>
                            <li><i class="fa fa-youtube-play" aria-hidden="true"></i></li>
                        </ul>
                    </div>
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

.footer-list ul li {
    font-size: 13px;
    padding-top: 10px;
    padding-right: 10px;
}
</style>