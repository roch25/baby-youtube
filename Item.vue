<template>
    <div class="item">
        <div class="image">
            <slot name="image" />
        </div>
        <div class="right">
             <div class="title">
                <slot name="title" />
            </div>
            <div class="channel">
                <slot name="channel" />
            </div>
            <div class="description">
                <slot name="description" />
            </div>
        </div> 
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.item {
    display: flex;
    margin: 0;
    cursor: pointer;
    border-bottom: 1px solid silver;
    padding: 10px;
    font-family: Arial, Helvetica, sans-serif;
    width: 100%;
}
.right {
    margin-left: 15px;
    display: flex;
    flex-direction: column;
}
.title{
    font-size: 3.8vmin;
    justify-self: flex-start;
    font-weight: 700;
}
.channel{
    font-size: 3.6vmin;
    justify-self: left;
    margin-top: 12px;
}
.description{
    margin-top: 12px;
    font-size: 2.6vmin;
}
</style>