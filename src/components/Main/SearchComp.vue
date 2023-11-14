<template>
    <select class="form-select" v-model="selectedArchetype" @change="emitArch">
        <option value="" selected>Select type</option>
        <option v-for="arch in archetypes" :key="arch" :value="arch">{{ arch }}</option>

    </select>
</template>

<script>
export default {
    name: 'SearchComp',
    data() {
        return {
            selectedArchetype: '',
            archetypes: ['Alien', 'Noble Knight', 'Melodious', 'Archfiend', 'A.I.', 'ABC']
        }
    },
    methods: {
        emitArch() {
            this.$emit('archSelected', this.selectedArchetype)
        }
    }
}
</script>

<style lang="scss" scoped>
select {
    width: 150px;
    margin: 20px;
}
</style>