<template>
  <HeaderComp />
  <MainComp />
</template>

<script>
import { store } from './data/store.js'
import HeaderComp from './components/Header/HeaderComp.vue';
import MainComp from './components/Main/MainComp.vue';
import axios from 'axios';
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
  },
  methods: {
    getCards() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then((response) => {
        store.cards = response.data
      })
      console.log(store.cards)
    }

  },
  created() {
    this.getCards()
  }
}
</script>

<style lang="scss" scoped></style>