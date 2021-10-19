<template>
  <section class="albums">
    <div class="container-fluid">
      <div class="row justify-content-center align-items-center"  v-if="!loading">
        <!-- ———— CARDS ———— -->
        <AlbumCard
        v-for="(album, index) in filteredAlbums"
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
import {eventBus} from '../main.js'

export default {
    name: 'Albums',
    components:{
      AlbumCard
    },
  data(){
    return {
        apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
        albums: [],
        test: [],
        loading: true,
        selectedGenre: 'All'
      }
  },
  created(){
      this.getAlbums(); 
      eventBus.$on('filters', el =>{
          this.selectedGenre = el;
      });     
  },
  computed:{
    filteredAlbums(){
        if(this.selectedGenre == 'All'){
          return this.albums;
        }
        return this.albums.filter(album => album.genre == this.selectedGenre);
    }
  },
  methods:{
      getAlbums(){
        axios
        .get(this.apiUrl)
        .then (response =>{
          this.albums = response.data.response;
          this.loading = false;
          this.selectedGenre = 'All';
          eventBus.$emit('selectGenre', this.albums);
        })
        .catch(err => console.log(err));
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