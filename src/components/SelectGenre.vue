<!-- HTML -->
<template>
    <div>
        <label for="genre">
            <span>Seleziona il genere</span>
            <select id="genre" v-model="selectedGenre" @change.prevent="changeGenre()">
                <option disabled selected >Genere</option>
                <option value="All">All</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>

        </label>
        
    </div>
    
</template>

<!-- JAVASCRIPT -->
<script>
export default {
    name: 'SelectGenre',
    data(){
        return{
            selectedGenre: 'All',
        }

    },

    methods:{
        changeGenre(){
            this.$emit('selectGenre', this.selectedGenre)
        }
    }
    
}
</script>

<!-- CSS -->
<style lang="scss" scoped>

label{

    span{
        padding: 10px;
        color: white;
    }
}

</style>