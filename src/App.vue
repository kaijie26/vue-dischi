<template>
  <div id="app">
    <HeaderSpotify />
    <AlbumList />

    
  </div>
</template>

<script>
import HeaderSpotify from './components/HeaderSpotify.vue'
import AlbumList from './components/AlbumList.vue'


export default {
  name: 'App',
  components: {
    HeaderSpotify,
    AlbumList,
    
    
  }
}
</script>

<style lang="scss">
@import './style/common';

</style>
