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
                            <li> <span><i class="fab fa-twitter"></i></span></li>
                            <li> <span><i class="fab fa-facebook-f"></i></span></li>
                            <li> <span><i class="fab fa-instagram"></i></span></li>
                            <li> <span><i class="fab fa-pinterest"></i></span></li>
                            <li> <span><i class="fab fa-youtube"></i></span></li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<style scoped>
footer {
    background-color: black;
    color: white;
    padding: 30px 0;
}

.footer-list ul li {
    font-size: 13px;
    padding-top: 10px;
    padding-right: 10px;
}
</style>