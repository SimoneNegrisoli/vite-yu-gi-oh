<template>
    <main>
        <div v-for="(card, index) in store.cards"> ciao</div>
    </main>
</template>

<script>
import { store } from '../../data/store.js';
export default {
    name: 'MainComp',
    data() {
        return {
            store,
        }
    }
}
</script>

<style lang="scss" scoped></style>