<template>
  <div class="movie">
      <h1>{{details.title}}</h1>
  </div>
</template>

<script>
export default {
  name: 'Movie',
  props: {
      details: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
   .movie {
       width: calc((100% / 4) - 40px);
       height: calc((100%) - 40px);
       background-color: white;
       margin: 20px;
   } 

</style>