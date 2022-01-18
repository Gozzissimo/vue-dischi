<template>
    <header class="flex">
        <img src="../assets/img/Spotify_logo_without_text.svg.png" alt="">
        <Select />
    </header>
</template>

<script>
import Select from "./Select.vue";

export default {
    name: "Header",
    components: {
        Select,
    },
}
</script>

<style lang="scss" scoped>
    @import "../assets/scss/partials/_variables.scss";

    header {
        background-color: $lightBgColor;
        align-items: center;
        padding: 1em;
        img {
            width: 3em;
        }
    }
</style>