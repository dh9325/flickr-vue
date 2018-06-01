<template>
    <nav>
        <div class="title"><span>Flickr Photo Stream</span></div>
    </nav>
</template>

<script>
  export default {
    name: 'NavBar',
  };
</script>

<style scoped>
    nav {
        position: fixed;
        width: 100%;
        height: 60px;
        top: 0;
        background-color: slateblue;
        color: white;
        margin-bottom: 50px;
    }
    .title {
        font-size: 22px;
        padding: 15px;
        font-weight: bold;
        transition: text-shadow 0.5s;
    }
    .title:hover {
        text-shadow: 0 0 10px;
    }
</style>