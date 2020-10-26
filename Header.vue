<template>
    <div class="header">
        <div class="logo">
            <img :src="logo" alt="logo">
            <div> {{label}} </div>
        </div>
        <div class="search-container">
             <input class="searchbar" type="text">
             <i class="fa fa-search searchicon" aria-hidden="true" title="Search"></i>
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

.header {
    display:flex;
    justify-content: space-between;
    margin: 2vw;
    width: 65vw;
    align-items: center;
}

.logo {
    display: flex;
    font-family: "Roboto Condensed", sans-serif;
    font-size: 4.5vmin;
    justify-content: space-around;
}

img {
    max-width: 30%;
    width: 8vw;
    height: 6vh;
}

.search-container {
    display: flex;
    align-items: center;
    width: 30vw;
    border-radius: 15px;
    border: 3px solid silver;
}

.search-container:hover{
  box-shadow: 1px 1px 2px 1px rgb(122, 122, 122);
}

.searchbar {
    height: 3vh;
    width: 25.8vw;
    margin: 0.75vw;
    border: none;
    outline: none;
    font-size: 3vmin;
}

.searchicon {
    cursor: pointer;
    position: relative;
    width: 3.2vw;
}

</style>
