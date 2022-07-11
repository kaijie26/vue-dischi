<!-- HTML -->
<template>
    <main>
        <div class="container">
            <!-- List genre bar -->
            <div class="album-genre">
                <SelectGenre @selectGenre="searchGenre" />
            </div>

            <!-- All album -->
            <div class="album-list" >
                <AlbumComponent v-for="(album, index) in filteredAlbumArray" :key="index" :infoAlbum="album" />
                
            </div>
        
        </div>

    </main>

</template>

<!-- JAVASCRIPT -->
<script>
import AlbumComponent from './AlbumComponent.vue'
import SelectGenre from './SelectGenre.vue'
import axios from 'axios'

export default {
    name: 'AlbumList',
    components: {
        AlbumComponent,
        SelectGenre,
    },

    data() {
        return{
            url: 'https://flynn.boolean.careers/exercises/api/array/music',
            albumArray: [],
            searchedGenre: 'All'
            

        }

    },

    computed:{
        filteredAlbumArray(){
            if(this.searchedGenre === 'All' ) {
                return this.albumArray;

            }

            return this.albumArray.filter((element) => {
                return element.genre.includes(this.searchedGenre)
            })
        }

    },

    created(){
            axios.get(this.url).then((response) => {
                this.albumArray = response.data.response;
                
                
            })

    },

    methods:{
        searchGenre(genre){
            this.searchedGenre = genre

        }
    }

    
}
</script>

<!-- CSS -->
<style lang="scss" scoped>
@import '../style/variables';

main{
    background-color: $page_main_secondary_color ;

    .album-list{
        display: flex;
        flex-wrap: wrap;
        padding: 50px 0;
    }

    .album-genre{
        text-align: center;
        padding-top: 30px;

    }
}

</style>