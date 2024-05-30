<script>
import HeaderComponent from './components/HeaderComponent.vue';
import FooterComponent from './components/FooterComponent.vue';

export default {
  name: "MyApp",
  components: {
    HeaderComponent,
    FooterComponent
  }
}
</script>

<template>
  <HeaderComponent />
  <FooterComponent />
</template>

<style lang="scss">
@use '../src/assets/styles/main.scss';
</style>
