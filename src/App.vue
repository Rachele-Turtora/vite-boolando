<script>
import HeaderComponent from './components/HeaderComponent.vue';

export default {
  name: "MyApp",
  components: {
    HeaderComponent
  }
}
</script>

<template>
  <HeaderComponent />
</template>

<style lang="scss">
@use '../src/assets/styles/main.scss';
</style>
