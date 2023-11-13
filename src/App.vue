<template>
  <HeaderComp />
  <MainComp />
</template>

<script>
import { store } from './data/store.js'
import HeaderComp from './components/Header/HeaderComp.vue';
import MainComp from './components/Main/MainComp.vue';
export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  data() {
    return {
      store
    }
  }
}
</script>

<style lang="scss" scoped></style>