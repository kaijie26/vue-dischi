<!-- HTML -->
<template>
    <main>
        <div class="container">
            <div class="album-list">
                <AlbumComponent v-for="(album, index) in albumArray" :key="index" :infoAlbum="album" />
                
            </div>
        
        </div>

    </main>

</template>

<!-- JAVASCRIPT -->
<script>
import AlbumComponent from './AlbumComponent.vue'
import axios from 'axios'

export default {
    name: 'AlbumList',
    components: {
        AlbumComponent
    },

    data() {
        return{
            url: 'https://flynn.boolean.careers/exercises/api/array/music',
            albumArray: [],

        }

    },

    mounted(){
            axios.get(this.url).then((response) => {
                this.albumArray = response.data.response
                
            })

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
}

</style>