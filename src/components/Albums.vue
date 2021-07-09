<template>
  <section class="albums">
    <div class="container-fluid">
      <div class="row justify-content-center align-items-center"  v-if="!loading">
        <!-- ———— CARDS ———— -->
        <AlbumCard
        v-for="(album, index) in albums"
        :key="index"
        :datas="album"/>
        <!-- ———— CARDS ———— -->
      </div>
      <div class="row justify-content-center align-items-center"  v-else>
        Loading...
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';

import AlbumCard from './AlbumCard.vue'

export default {
    name: 'Albums',
    components:{
      AlbumCard
    },
  data(){
    return {
        apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
        albums: '',
        loading: true
      }
  },
  created(){
      this.getAlbums();
      this.$emit('selectGenre',this.getAlbums());
  },
  methods:{
      getAlbums(){
        axios
        .get(this.apiUrl)
        .then (response =>{
          this.albums = response.data.response;
          this.loading = false;
        })
      }
  }
}
</script>

<style lang="scss" scoped>
@import '@/style/general.scss';
@import '@/style/vars.scss';

.albums{
    width:100%;
    background-color:$primary_dark;
    padding:70px 5%;
}
</style>