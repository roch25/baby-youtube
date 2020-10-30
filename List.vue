<template>
  <div class="list">
      <list-item v-for="item in searchResults" :key="item.id.videoId">
           <template v-slot:image>
                <img :src="item.snippet.thumbnails.medium.url"/>
            </template>
            <template v-slot:title>
                {{item.snippet.title}}
            </template>
            <template v-slot:channel>
                {{item.snippet.channelTitle}}
            </template>
             <template v-slot:description>
                {{item.snippet.description}}
            </template>
      </list-item>
  </div>
</template>

<script>
import ListItem from './Item.vue'
export default {
    props:{
        searchResults:{
            type: Array
        }
    },
    components:{
        ListItem
    }
}
</script>

<style scoped>
</style>