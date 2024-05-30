<script>
export default {
    name: "Header"
}
</script>

<template>
    <header>
        <div class="container">
            <div class="row">
                <div class="col-33">
                    <div class="header-list">
                        <ul>
                            <li><a href="#">Donna</a></li>
                            <li><a href="#">Uomo</a></li>
                            <li><a href="#">Bambini</a></li>
                        </ul>
                    </div>
                </div>
                <div class="col-33">
                    <div class="logo">
                        <img src="../../img/boolean-logo.png" alt="logo">
                    </div>
                </div>
                <div class="col-33 text-right">
                    <div class="header-list">
                        <ul>
                            <li><a href="#"><i class="fas fa-user"></i></a></li>
                            <li><a href="#"><i class="fas fa-heart"></i></a></li>
                            <li><a href="#"><i class="fas fa-bag-shopping"></i></a></li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<style scoped>
header {
    position: fixed;
    width: 100%;
    background-color: rgb(255, 94, 0);
    z-index: 1;
    padding-top: 10px;
}

.text-right {
    text-align: right;
}

a {
    color: white;
    text-decoration: none;
}

.header-list ul li {
    font-size: 20px;
    padding: 0 10px;
}

.logo {
    width: 40%;
    margin: 0 auto;
}
</style>