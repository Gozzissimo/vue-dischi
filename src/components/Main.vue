<template>
    <main>
        <Select 
            @selectGenre="filterGenre($event)"
            @selectArtist="filterArtist($event)"
        />
        <div v-if="cards">
            <ul class="container flex" >
                <Card 
                    v-for="(card, index) in filteredCards" 
                    :key="index"
                    :image="card.poster"
                    :imageAlt="card.title + ' - ' + card.author"
                    :heading2="card.title"
                    :heading3="card.author"
                    :heading4="card.year"
                />
            </ul>
        </div>
        <div v-else>
            <p class="text-center">Loading...</p>
        </div>
    </main>
</template>

<script>
import Card from "./Card.vue";
import Select from "./Select.vue";
import axios from 'axios';

export default {
    name: "Main",
    components: {
        Card,
        Select,
    },
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) => {
                console.log(result);
                this.cards = result.data.response;
                this.filteredCards = result.data.response;

                // "poster": "https://m.media-amazon.com/images/I/71K9CbNZPsL._SS500_.jpg",
                // "title": "Bad",
                // "author": "Michael Jacjson",
                // "genre": "Pop",
                // "year": "1987"

            })
            .catch((error) => {
                console.log(error);
            });
    },

    computed: {
        filteredCards(){
            if(this.genreSelected == '' && this.artistSelected == ''){
                return this.cards;
            } else if (this.genreSelected !== '' && this.artistSelected == '') {
                return this.cards.filter((element) => element.genre == this.genreSelected);
            } else if (this.genreSelected == '' && this.artistSelected !== '') {
                return this.cards.filter((element) => element.author == this.artistSelected);
            } else {
                return this.cards.filter((element) => element.genre == this.genreSelected && element.author == this.artistSelected);
            }
        }
    },

    data() {
        return {
            cards: null,
            genreSelected: '',
            artistSelected: '',
        }
    },

    methods: {
        filterGenre(input) {
            this.genreSelected = input;
        },

        filterArtist(input) {
            this.artistSelected = input;
        }
    }
}
</script>

<style lang="scss" scoped>
    @import "../assets/scss/partials/_variables.scss";

    main {
        background-color: $darkBgColor;
        .container {
            flex-wrap: wrap;
            padding: 4em 0;
        }
    }
</style>