<template>
    <div class="album col-4 col-lg-2">
        <img :src="datas.poster" :alt="datas.title">
        <p class="title">{{datas.title}}</p>
        <p class="info">{{datas.author}} <br> {{datas.year}}</p>
    </div>
</template>

<script>
export default {
    name: 'AlbumCard',
    props: ["datas"]
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