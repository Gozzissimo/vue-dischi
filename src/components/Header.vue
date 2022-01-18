<template>
    <header class="flex">
        <img src="../assets/img/Spotify_logo_without_text.svg.png" alt="">
    </header>
</template>

<script>
export default {
    name: "Header",
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