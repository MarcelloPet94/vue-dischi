<template>
  <div class="main_container">
      <div class="grid_playlist">
          <Thumb/>
          <Thumb/>
          <Thumb/>
          <Thumb/>
          <Thumb/>
      </div>
  </div>
</template>

<script>

import Thumb from './partials/Thumb.vue';

export default {

  name: 'Main',
  components:{
    Thumb
  }
}
</script>

<style scoped lang="scss">

.main_container
{
  display: flex;
  justify-content: center;
}

.grid_playlist
{
  display: grid;
  grid-template-columns: auto auto auto auto auto;
  grid-gap: 16px;
  padding: 0 16px;
  width: auto;
  border: 1px solid blue;

}

</style>
