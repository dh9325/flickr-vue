<template>
    <div id="app">
        <nav-bar></nav-bar>
        <photo-container></photo-container>
    </div>
</template>

<script>
  import NavBar from './components/NavBar.vue';
  import PhotoContainer from './components/PhotoContainer.vue';
  import PhotoCard from './components/PhotoCard';

  export default {
    name: 'app',
    components: {
      NavBar,
      PhotoContainer,
      PhotoCard,
    },
  };
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        color: #2c3e50;
        margin-top: 60px;
        box-sizing: border-box;
    }
    body {
        margin: 0;
    }
</style>
