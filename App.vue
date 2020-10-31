<template>
    <div class="container">
        <app-header logo="./images/logo.png" label='YouTube' @onClickSearch="fetchSearchList"/>
        <div class="body">
            <video-player v-show="showVideo" :selectedVideoId="selectedVideoId"/>
            <list :searchResults="searchResults" @videoSelected="getSelectedVideo"/>
        </div>
    </div>
</template>

<script>
import AppHeader from './Header.vue'
import VideoPlayer from './Video.vue';
import List from './List.vue'
let key = import.meta.env.VITE_API_KEY
const url = "https://www.googleapis.com/youtube/v3";
export default {
    components : {
        AppHeader,
        List,
        VideoPlayer
    },
    data(){
        return{
            searchResults: [],
            selectedVideoId: 'https://www.youtube.com/embed/',
            showVideo: false
        }
    },
    methods:{
        async fetchSearchList(query){
            key = key.replace(/[;]/g, "") // fix
            const response = await fetch(url+"/search?key="+key+"&q="+query+"&part=snippet&type=video&maxResults=10");
            const data = await response.json();
            this.searchResults = data.items
        },
        getSelectedVideo(payload){
            this.selectedVideoId = this.selectedVideoId.concat(payload.id.videoId);
            this.showVideo = true
        }
    }
}
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