<template>
    <div class="container">
        <app-header logo="./images/logo.png" label='YouTube' @onClickSearch="fetchSearchList"/>
        <div class="body">
             <!-- video player, hidden initially -->
            <list />
        </div>
    </div>
</template>

<script>
import AppHeader from './Header.vue'
import List from './List.vue'
let key = import.meta.env.VITE_API_KEY
const url = "https://www.googleapis.com/youtube/v3";
export default {
    components : {
        AppHeader
    },
    data(){
        return{
            searchResults: []
        }
    },
    methods:{
        async fetchSearchList(query){
            key = key.replace(/[;]/g, "") // fix
            const response = await fetch(url+"/search?key="+key+"&q="+query+"&part=snippet&type=video&maxResults=10");
            const data = await response.json();
            this.searchResults = data.items
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