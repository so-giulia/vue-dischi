<template>
  <div id="app">
    <Header/>
    <main>
      <Albums/>
    </main>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Albums from './components/Albums.vue';

export default {
  name: 'App',
  components:{
    Header,
    Albums
  }
}
</script>

<style lang="scss">
@import '@/style/general.scss';
@import '@/style/vars.scss';

#app{

  main{
    width:100%;
    background-color:$primary_dark;
    padding:70px 8%;
  }
}

</style>
