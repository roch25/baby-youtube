<template>
  <iframe 
    width="560" 
    height="315" 
    :src="selectedVideoId" 
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen>
  </iframe>
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
</style>