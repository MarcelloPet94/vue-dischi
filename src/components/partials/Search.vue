<template>
<div class="filters_ontainer">
  <select  class="filters_select" @change="passaGenere">
    <option>Tutti i generi</option>
    <option>jazz</option>
    <option>rock</option>
    <option>metal</option>
    <option>pop</option>
  </select>
</div>
</template>

<script>
export default {
  name: 'Thumb',
  data() {
    return {
      genere: ''
    }
  },
  methods:{
    passaGenere : function(e) {
      this.genere = e.target.value
      this.$emit('filtraggio' , this.genere)
    }
  }
}
</script>

<style scoped lang="scss">

.filters_ontainer
{
padding-top: 24px;
background-color: #1e2d3b;

.filters_select
  {
    position: relative;
    left: 15%;
    width: 70%;
    padding: 16px;
        

  }
}

</style>
