<template>
  <header>
      <div class="container-fluid">
          <div class="logo-container row align-items-center">
            <div class="col-2">
                <img id="logo" src="../img/logo-green.svg" alt="Logo Spotify Green">
            </div>
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
    
    width:100%;
    background-color:$primary_light;

    .logo-container{
        height:70px;
        padding:10px 0;
        #logo{
            width:60px;
            height:40px;
        }
    }
}

</style>