<template>
  <div class="list">
      <list-item 
        v-for="item in searchResults" 
        :key="item.videoId" 
        @click="selected(item)">
            <template v-slot:image>
                <img :src="item.thumbnail"/>
            </template>
            <template v-slot:title>
                {{item.title}}
            </template>
            <template v-slot:channel>
                {{item.channelTitle}}
            </template>
             <template v-slot:description>
                {{item.description}}
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
    },
    methods:{
        selected(videoPayload){
            this.$emit('videoSelected', videoPayload)
        }
    }
}
</script>

<style scoped>
.list{
    margin: 2.5vmin;
}
</style>