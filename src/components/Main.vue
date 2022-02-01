<template>
  <div class="main">
    <Search @filtraggio = 'filtraGenere'

    />
    <div class="thumb_container">
        <div class="grid_playlist" v-if="selectedInput != '' && selectedInput != 'Tutti i generi' ">
              <Thumb v-for="artist in arrayFiltrato" :key="artist.id"
                :spotifyApi="artist"
              />
        </div>

        <div class="grid_playlist" v-else>
              <Thumb v-for="artist in spotifyData" :key="artist.id"
                :spotifyApi="artist"
              />
        </div>


    </div>
  </div>
</template>

<script>
import axios from 'axios'
import Search from './partials/Search.vue' 
import Thumb from './partials/Thumb.vue';

export default {

  name: 'Main',
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      spotifyData : [],
      selectedInput: ''
    }
  },
  components:{
    Thumb,
    Search
  },
  created(){
    this.getData()
  },
  methods: {
    getData: function(){
      axios.get(this.apiUrl)
      .then((allData) => {
        this.spotifyData = allData.data.response
      })
      .catch(function (error) {
        console.log(error)
      })
    },

    filtraGenere: function(genere){
      this.selectedInput = genere
      console.log(this.selectedInput)
    }
  },
  computed: {
    arrayFiltrato() {
      console.log(this.spotifyData)
      console.log(this.spotifyData.filter(disco => disco.genre == this.selectedInput))
      return this.spotifyData.filter(disco => disco.genre.toLowerCase() == this.selectedInput)
    }
  }
  
}
</script>

<style scoped lang="scss">

.main
{

  .thumb_container
  {
    display: flex;
    justify-content: center;
    background-color: #1e2d3b;
    padding-top: 24px;
  }

  .grid_playlist
  {
    display: grid;
    grid-template-columns: auto auto auto auto auto;
    grid-gap: 16px;
    padding: 0 16px;
    width: auto;

  }
}
</style>
