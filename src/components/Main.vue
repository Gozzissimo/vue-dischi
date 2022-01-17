<template>
    <main>
        <ul class="container flex">
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
            <Card />
        </ul>
    </main>
</template>

<script>
import Card from "./Card.vue";

export default {
    name: "Main",
    components: {
        Card,
    },

    data() {
        return {

        }
    }
}
</script>

<style lang="scss" scoped>
    @import "../assets/scss/partials/_variables.scss";

    main {
        background-color: $darkBgColor;
        height: calc(100vh - 80px);
        .container {
            flex-wrap: wrap;
            padding: 4em 0;
        }
    }
</style>