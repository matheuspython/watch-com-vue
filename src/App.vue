<template>
  <TheHeader />
  <TheMain />
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheMain from './components/TheMain.vue';

export default {
  name: 'App',
  components: {
    TheHeader,
    TheMain
}
}
</script>

<style>
#app {
  font-family: sans-serif,Avenir, Helvetica, Arial;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
</style>
