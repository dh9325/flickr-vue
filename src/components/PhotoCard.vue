<template>
    <div class="card">
        <img class="card-img" :src="photo.media.m">
        <div class="card-title">
            <span>
                <a :href="photo.link" target="_blank">{{photo.title}}</a> by
                <a :href="authorLink" target="_blank">{{authorName}}</a></span>
        </div>
        <div class="card-description">
            <strong>Description: </strong>
        </div>
        <div class="card-tags">
            <strong>Tags: </strong><span v-for="tag in tags" v-bind:key="tag">{{tag}} </span>
        </div>
    </div>
</template>

<script>
  export default {
    name: 'PhotoCard',
    props: {
      photo: Object,
    },
    computed: {
      authorLink: {
        get() {
          return `https://www.flickr.com/people/${this.photo.author_id}/`;
        },
      },
      authorName: {
        get() {
          return this.getAuthorName(this.photo.author);
        },
      },
      tags: {
        get() {
          return this.photo.tags.split(' ');
        },
      },
    },
    mounted() {
      // console.log(this.photo);
    },
    methods: {
      getAuthorName: (author) => {
        const matches = author.match(/".+"/);
        if (matches && matches.length) {
          return matches[0].replace(/"/g, '');
        }
        return author;
      },
    },
  };
</script>

<style scoped>
    .card {
        width: 250px;
        height: 350px;
        box-shadow: 0 4px 8px 0 slateblue, 0 6px 20px 0 slateblue;
        margin: 5px;
        padding: 10px;
    }
    .card-img {
        width: 100%;
        height: 50%;
    }
</style>