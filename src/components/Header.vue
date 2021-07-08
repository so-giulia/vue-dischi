<template>
  <header class="row align-items-center">
      <img id="logo" src="../img/logo-green.svg" alt="Logo Spotify Green">
  </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style lang="scss" scoped>
@import '@/style/general.scss';
@import '@/style/vars.scss';
header{
    height:70px;
    background-color:$primary_light;
    padding:10px 0 10px 10px;

    #logo{
        width:auto;
        height:40px;
    }
}

</style>