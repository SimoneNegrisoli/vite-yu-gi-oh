<template>
    <main>
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <SearchComp @archSelected="getArch" />
                </div>
            </div>
            <div class="row my-row-card">
                <div class="col-12" v-if="(store.cards.length < 20)">
                    loading
                </div>
                <div v-else v-for="(card, index) in store.cards" class=" col-12 col-md-2 text-center my-3 mx-1 ">
                    <CardComp :image="card.card_images[0].image_url" :title="card.name" :text="card.archetype" />
                </div>
            </div>
        </div>

    </main>
</template>

<script>
import SearchComp from './SearchComp.vue'
import { store } from '../../data/store.js';
import CardComp from './CardComp.vue';
export default {
    name: 'MainComp',
    components: {
        CardComp,
        SearchComp
    },
    data() {
        return {
            store,
            filteredCard: []
        }
    },
    methods: {
        getArch(selectedArchetype) {
            if (selectedArchetype === 'Select type') {
                this.filteredCards = [this.store.cards];
            } else {
                this.filteredCard = this.store.cards.filter(card => card.archetype === selectedArchetype);
                console.log(this.filteredCard)
            }
        }
    },
    created() {
        this.getArch()
    }
}
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables.scss' as *;


main {
    background-color: $colororange;
}

.row {
    justify-content: center;
}

.my-row-card {
    border: 1px solid black;
    background-color: white;
    padding-top: 60px;

}
</style>