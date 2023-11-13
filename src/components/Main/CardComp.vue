<template>
    <div class="card" style="width: 18rem;">
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
    props: [
        image = String,
        title = String,
        text = String
    ]
}
</script>

<style lang="scss" scoped></style>