<template>
  <section class="albums">
    <div class="row justify-content-center align-items-center">
      <!-- ———— CARD ———— -->
      <div class="album col-4 col-lg-2" v-for="(album, index) in albums" :key="index">
        <img :src="album.poster" :alt="album.title">
        <p class="title">{{album.title}}</p>
        <p class="info">{{album.author}} <br> {{album.year}}</p>
      </div>
      <!-- ———— CARD ———— -->
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
        })
      }
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/general.scss';
@import '@/style/vars.scss';

.album{
  background-color:$primary_light;
  color: $light;
  padding:20px;
  text-align: center;
  height: 400px;
  margin:0 20px 50px 20px;

  img{
    width:100%;
  }

  .title{
    color: $light;
    font-weight:600;
    text-transform: uppercase;
    margin:10px 0;
  }

  .info{
    color: $grey;
    font-size:.8rem;
  }
}
</style>