<template>
  <div class="container">
    <app-header
      logo="./images/logo.png"
      label="YouTube"
      @onClickSearch="fetchSearchList"
    />
    <div class="body">
      <video-player v-show="showVideo" :selectedVideoId="selectedVideoId" />
      <list :searchResults="searchResults" @videoSelected="getSelectedVideo" />
    </div>
  </div>
</template>

<script>
import AppHeader from "./Header.vue";
import VideoPlayer from "./Video.vue";
import List from "./List.vue";
const key = import.meta.env.VITE_API_KEY;
const url = "https://www.googleapis.com/youtube/v3";
const urlEmb = "https://www.youtube.com/embed/";
export default {
  components: {
    AppHeader,
    List,
    VideoPlayer,
  },
  data() {
    return {
      searchResults: [],
      selectedVideoId: urlEmb,
      showVideo: false,
    };
  },
  methods: {
    async fetchSearchList(query) {
      key.slice(0, -1);
      const response = await fetch(
        url +
          "/search?key=" +
          key +
          "&q=" +
          query +
          "&part=snippet&type=video&maxResults=10"
      );
      const data = await response.json();
      this.searchResults = data.items.map((item) => ({
        videoId: item.id.videoId,
        title: item.snippet.title,
        thumbnail: item.snippet.thumbnails.medium.url,
        channelTitle: item.snippet.channelTitle,
        description: item.snippet.description,
      }));
    },
    getSelectedVideo(payload) {
      this.selectedVideoId = this.selectedVideoId + payload.videoId;
      this.showVideo = true;
    },
  },
};
</script>

<style>
* {
  color: white;
  background-color: rgb(36, 36, 36);
}

.body {
  display: flex;
}
</style>
