<template>
    <div>
        <select 
            v-model="selectedGenre" 
            @change="$emit('selectGenre', selectedGenre)"
            name="genres" 
            id="genres">
                <option value="">All</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
        </select>
    </div>
</template>

<script>
export default {
    name: "Select",
    data() {
        return {
            selectedGenre: '',
        };
    },
}
</script>

<style>

</style>