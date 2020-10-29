<template>
    <div class="container">
        <app-header logo="./images/logo.png" label='YouTube' />
        <div class="body">
             <!-- video player, hidden initially -->
            <list/>
        </div>
    </div>
</template>

<script>
import AppHeader from './Header.vue'
import List from './List.vue'
export default {
    components : {
        AppHeader,
        List
    }
}
</script>

<style>
    *{
        color: white;
        background-color: rgb(36, 36, 36);
    }

    .body {
        display: flex;
    }
</style>