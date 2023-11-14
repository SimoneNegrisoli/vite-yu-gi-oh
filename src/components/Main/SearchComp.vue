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
            archetypes: []
        }
    },
    mounted() {
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then((response) => {
                this.archetypes = response.data.data.map(item => item.archetype_name);
            })
            .catch(error => {
                console.error('Errore :', error);
            })

    },
    methods: {
        emitArch() {
            this.$emit('archSelected', this.selectedArchetype)
            console.log(this.selectedArchetype)
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