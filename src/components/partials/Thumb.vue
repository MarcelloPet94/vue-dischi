<template>
        <div class="box_album">
            <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg">
            <h3>ALBUM</h3>
            <p>ARTISTA</p>
        </div>
</template>

<script>
export default {
  name: 'Thumb'
}
</script>

<style scoped lang="scss">

.box_album
{
    width: 200px;
    padding: 16px;
    margin-bottom: 16px;
    text-align: center;
    background-color: lightblue;

    img
    {
        width: 100%;
    }
}

</style>
