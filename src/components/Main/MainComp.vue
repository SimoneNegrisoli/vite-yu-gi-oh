<template>
    <main>
        <div v-for="(card, index) in store.cards">
            <CardComp :image="card.card_images[0].image_url" />
        </div>
    </main>
</template>

<script>
import { store } from '../../data/store.js';
import CardComp from './CardComp.vue';
export default {
    name: 'MainComp',
    components: {
        CardComp
    },
    data() {
        return {
            store,
        }
    }
}
</script>

<style lang="scss" scoped></style>