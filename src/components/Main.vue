<template>
    <main>
        <ul class="container flex">
            <Card />
        </ul>
    </main>
</template>

<script>
import Card from "./Card.vue";
import axios from 'axios';

export default {
    name: "Main",
    components: {
        Card,
    },
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) => {
                console.log(result);
            })
            .catch((error) => {
                console.log(error);
            });
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