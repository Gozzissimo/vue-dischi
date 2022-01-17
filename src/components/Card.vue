<template>
    <li class="card flex">
        <div class="card-img">
            <img src="" alt="">
        </div>
        <div class="card-txt text-center">
            <h2 class="album">ALBUM</h2>
            <h3 class="artist">Artista</h3>
            <h4 class="year">Anno</h4>
        </div>
    </li>
</template>

<script>
export default {
    name: "Card",
}
</script>

<style lang="scss" scoped>
    @import "../assets/scss/partials/_variables.scss";
    .card {
        background-color: $lightBgColor;
        margin: 1em;
        flex-basis: calc((100% / 5) - 2em);
        flex-direction: column;
        align-items: center;
        .card-img {
            width: 150px;
            height: 150px;
            margin: 1em;
            background-color: salmon;
        }
        .card-txt {
            margin: 1em;
            .album {
                color: $whiteFontColor;
            }
            .artist, .year {
                color: $greyFontColor;
                font-size: 0.8em;
            }
        }
    }
</style>