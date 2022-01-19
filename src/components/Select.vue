<template>
    <div class="filters flex">
        <h1>Genres</h1>
        <select 
            v-model="selectedGenre" 
            @change="$emit('selectGenre', selectedGenre)"
            name="genres" 
            id="genres">
                <option value="">All</option>
                <option 
                    v-for="(card, index) in cards"
                    :key="index" 
                    :value="card.genre">
                        {{ card.genre }}
                </option>
        </select>

        <h1>Artists</h1>
        <select 
            v-model="selectedArtist" 
            @change="$emit('selectArtist', selectedArtist)"
            name="artists" 
            id="artists">
                <option value="">All</option>
                <option 
                    v-for="(card, index) in cards"
                    :key="index" 
                    :value="card.author">
                        {{ card.author }}
                </option>
        </select>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: "Select",
    data() {
        return {
            selectedGenre: '',
            selectedArtist: '',
            cards: null,
        };
    },

    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) => {
                console.log(result);
                this.cards = result.data.response;
            })
            .catch((error) => {
                console.log(error);
            });
    },
}
</script>

<style lang="scss" scoped>
    @import "../assets/scss/partials/_variables.scss";

    .filters {
        padding: 2em;
        align-items: center;
        justify-content: flex-end;
        h1 {
            color: $whiteFontColor;
        }
        select {
            width: 100px;
            height: 2em;
            margin: 1em;
            font-size: 1em;
            border-radius: 5px;
            text-align: center;
            background-color: $darkBgColor;
            color: $greyFontColor;
        }
    }
</style>