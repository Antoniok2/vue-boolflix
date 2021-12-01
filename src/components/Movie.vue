<template>
  <div class="movie">
      <img src="" alt="">
  </div>
</template>

<script>
export default {
  name: 'Movie',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
   .movie {
       width: calc((100% / 4) - 20px);
       height: calc((100%) - 40px);
       background-color: white;
       margin: 20px;
   } 

</style>