<template>
    <div>
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

                <!-- <option value="Rock">Rock</option>
                <option value="Pop">Pop</option> -->
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

<style>

</style>