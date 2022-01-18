<template>
    <div>
        <select 
            v-model="selected" 
            @change="$emit('selectGenre', selectedGenre)"
            name="genre" 
            id="genre">
                <option disabled value="">All</option>
                <option value="2">Rock</option>
                <option value="3">Pop</option>
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