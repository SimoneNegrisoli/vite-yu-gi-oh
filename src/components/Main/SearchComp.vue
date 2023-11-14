<template>
    <select class="form-select">
        <option selected>Select type</option>
        <option value="1">One</option>
        <option value="2">Two</option>
        <option value="3">Three</option>
    </select>
</template>

<script>
export default {
    name: 'SearchComp'
}
</script>

<style lang="scss" scoped>
select {
    width: 150px;
    margin: 20px;
}
</style>