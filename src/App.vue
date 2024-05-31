<script>
import HeaderComponent from './components/HeaderComponent.vue';
import ProductsList from './components/ProductsList.vue';
import FooterComponent from './components/FooterComponent.vue';

export default {
  name: "MyApp",
  components: {
    HeaderComponent,
    FooterComponent,
    ProductsList
  }
}
</script>

<template>
  <HeaderComponent />
  <main>
    <ProductsList />
  </main>
  <FooterComponent />
</template>

<style lang="scss">
@use '../src/assets/styles/main.scss';
</style>
