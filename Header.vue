<template>
    <div class="header">
        <div class="logo">
            <img :src="logo" alt="logo">
            <div> {{label}} </div>
        </div>
        <div class="searchbox">

        </div>
    </div>
</template>

<script>
export default {
    props: { 
        logo: {
            type: String
        },
        label: {
            type: String
        }
    },
}
</script>

<style>
.logo {
    display: flex;
}

img {
    max-width: 30%;
    width: 9vh;
    height: 6vmin;
}

.logo {
    font-family: "Roboto Condensed", sans-serif;
    font-size: 4.5vmin;
}

</style>
