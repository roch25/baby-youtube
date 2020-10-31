<template>
 <div class="player">
    <iframe 
        width="660" 
        height="355" 
        :src="selectedVideoId" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen>
    </iframe>
  </div>
</template>

<script>
export default {
    props: {
        selectedVideoId: {
            type: String
        }
    }
}
</script>

<style scoped>
iframe {
    margin: 3vmin;
}

.player{
    padding: 2vh;    
    width: 100%;
}
</style>