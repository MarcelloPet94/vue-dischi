<template>
        <div class="box_album">
            <img :src="spotifyApi.poster">
            <h3>{{spotifyApi.title}}</h3>
            <p>{{spotifyApi.author}}</p>
        </div>
</template>

<script>
export default {
  name: 'Thumb',
  props:{
    spotifyApi: Object
  }
}
</script>

<style scoped lang="scss">

.box_album
{
    width: 200px;
    padding: 16px;
    margin-bottom: 16px;
    text-align: center;
    background-color: #2e3a46;
    color: #fff;

    img
    {
        width: 100%;
    }
}

</style>
