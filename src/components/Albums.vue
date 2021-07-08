<template>
  <section class="albums">
    <div class="row">
      <div class="album" v-for="(album, index) in albums" :key="index">
        Prova
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Albums',
    data(){
      return {
        apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
        albums: ''
      }
    },
    created(){
      this.getAlbums();
    },
    methods:{
      getAlbums(){
        axios
        .get(this.apiUrl)
        .then (response =>{
          this.albums = response.data.response;
          console.log(this.albums);
        })
      }
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/general.scss';
@import '@/style/vars.scss';

.album{
  color: $light;
}
</style>