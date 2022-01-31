<template>
  <div class="main_container">
      <div class="grid_playlist" >
            <Thumb v-for="artist in spotifyData" :key="artist.id"
              :cover="artist.poster"
              :album="artist.title"
              :author="artist.author"
            />
      </div>
  </div>
</template>

<script>
import axios from 'axios'
import Thumb from './partials/Thumb.vue';

export default {

  name: 'Main',
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      spotifyData : []
    }
  },
  components:{
    Thumb
  },
  created(){
    this.getData()
  },
  methods: {
    getData: function(){
        axios.get(this.apiUrl)
        .then((allData) => {
          console.log(allData.data.response)
          this.spotifyData = allData.data.response
        })
        .catch(function (error) {
          console.log(error)
        })
    }
  }
  
}
</script>

<style scoped lang="scss">

.main_container
{
  display: flex;
  justify-content: center;
  background-color: #1e2d3b;
}

.grid_playlist
{
  display: grid;
  grid-template-columns: auto auto auto auto auto;
  grid-gap: 16px;
  padding: 0 16px;
  width: auto;

}

</style>
