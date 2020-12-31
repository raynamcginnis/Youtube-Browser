<template>
  <li class="list-group-item media" @click="onVideoSelect">
    <img class="mr-3" :src="thumbnailUrl" />
    <div class="media-body snippet">
      {{ video.snippet.title }}
    </div>
  </li>
</template>

<script>
export default {
  name: 'VideoListItem',
  props: ['video'],
  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.default.url;
    }
  },
  methods: {
    onVideoSelect() {
      this.$emit('videoSelect', this.video);
    }
  }
};
</script>


<!-- scoped means that the css will only effect THIS component -->
<style scoped>
li {
    display: flex;
    cursor: pointer;

}
li:hover {
    background-color: #eee;
}

.snippet {
   padding: 10px;

}


</style>