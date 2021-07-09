<template>
  <header>
      <div class="container-fluid">
          <div class="header-items-container row align-items-center justify-content-between">
            <div class="col-2">
                <img id="logo" src="../img/logo-green.svg" alt="Logo Spotify Green">
            </div>
            
            <Filters/>
        </div>
      </div>
    
  </header>
</template>

<script>
import Filters from './Filters.vue'

export default {
    name: 'Header',
    components:{
        Filters
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/general.scss';
@import '@/style/vars.scss';

header{
    width:100%;
    background-color:$primary_light;

    .header-items-container{
        height:70px;
        padding:10px 0;

        #logo{
            width:60px;
            height:40px;
        }
    }
}

</style>