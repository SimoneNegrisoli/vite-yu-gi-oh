<template>
    <main>
        <div class="container">
            <div class="row">
                <div v-for="(card, index) in store.cards" class=" col-12 col-md-2 text-center my-3 mx-1 ">
                    <CardComp :image="card.card_images[0].image_url" :title="card.name" :text="card.archetype" />
                </div>
            </div>
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

<style lang="scss" scoped>
.row {
    background-color: white;
    padding: 50px;
    justify-content: center;
}
</style>