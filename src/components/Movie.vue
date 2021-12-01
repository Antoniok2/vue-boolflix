<template>
  <div class="movie">
      <h1><strong>Titolo:</strong> {{details.title}}</h1>
      <h2><strong>Titolo originale:</strong> {{details.original_title}}</h2>
      <h2><strong>Language:</strong> {{details.original_language}}</h2>
      <h2><strong>Voto:</strong> {{details.vote_average}}</h2>
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
       background-color: black;
       margin: 20px;

       h1 {
           color: white;
           font-size: 20px;
       }

       h2 {
           color: white;
           font-size: 15px;
           margin: 10px 0;
       }
   } 

</style>