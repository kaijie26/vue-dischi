<template>
    <div class="card">
        <img :src="infoAlbum.poster" :alt="infoAlbum.genre">

        <h3>{{ infoAlbum.title}}</h3>

        <div>{{  infoAlbum.author}}</div>
        
        <div> {{ infoAlbum.year}}</div>
        
    </div>
    
</template>

<script>
export default {
    name:'AlbumComponent',
    props: {
        infoAlbum: Object
    }

    
}
</script>

<style lang="scss" scoped>
@import '../style/variables';

.card{
    width: calc((100% / 5) - 20px);
    margin: 10px;
    background-color: $page_main_primary_color;
    padding: 20px;
    text-align: center;

    h3{
        color: white;
        padding: 10px 0;
    }

    div{
        color: lightgray;
    }

    img{
        width: 100%;
    }
}

</style>