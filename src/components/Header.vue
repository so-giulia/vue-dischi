<template>
  <header>
    <div class="row align-items-center">
        <div class="col-12">
            <img id="logo" src="../img/logo-green.svg" alt="Logo Spotify Green">
        </div>
    </div>
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
    width:100%;
    background-color:$primary_light;
    padding:10px 0;

    #logo{
        width:60px;
        height:40px;
    }
}

</style>