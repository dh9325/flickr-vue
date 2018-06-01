<template>
    <div class="container">
        <photo-card class="card" v-for="item in photos" v-bind:photo="item" v-if="photos.length"></photo-card>
    </div>
</template>

<script>
  import PhotoCard from './PhotoCard';

  export default {
    name: 'PhotoContainer',
    components: {PhotoCard},
    data: () => {
      return {
        photos: [],
      };
    },
    mounted() {
      this.$jsonp('https://api.flickr.com/services/feeds/photos_public.gne?format=json', {
        callbackQuery: 'cb', callbackName: 'jsonFlickrFeed',
      }).then((res) => {
        this.photos = res.items;
      });
    },
  };
</script>

<style scoped>
    .container {
        padding-left: 60px;
        margin: auto;
    }
    .card {
        float: left;
    }
</style>