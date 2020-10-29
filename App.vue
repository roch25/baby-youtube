<template>
  <app-header logo="./images/logo.png" label='YouTube' @onClickSearch="fetchSearchList"/>
</template>

<script>
import AppHeader from './Header.vue'
export default {
    components : {
        AppHeader
    },
    methods:{
        fetchSearchList(query){
            console.log(query + "from app");
        }
    }

}
</script>

<style>
    * {
        color: white;
        background-color: rgb(36, 36, 36);
    }
</style>