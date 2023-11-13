<template>
    <div class="card">
        <img :src="image" class="card-img-top" :alt="title">
        <div class="card-body">
            <h5 class="card-title">{{ title }}</h5>
            <div class="card-text">
                {{ text }}
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'CardComp',
    props: {
        image: 'String',
        title: 'String',
        text: 'String'
    }

}
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables.scss' as *;

div {
    .card-body {
        height: 120px;
        background-color: $colororange ;
    }

    h5 {
        font-size: 1rem;
        font-weight: bolder;
        color: white;
    }
}
</style>