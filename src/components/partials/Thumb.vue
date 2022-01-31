<template>
        <div class="box_album">
            <img :src="cover">
            <h3>{{author}}</h3>
            <p>{{album}}</p>
        </div>
</template>

<script>
export default {
  name: 'Thumb',
  props:{
      cover: String,
      author: String,
      album: String
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
