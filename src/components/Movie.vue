<template>
  <div class="movie">
      <h1><strong>Titolo:</strong> {{details.title}}</h1>
      <h2><strong>Titolo originale:</strong> {{details.original_title}}</h2>
      <h2 v-if="details.original_language === 'en'"><strong>Language:</strong><img src="../assets/englishflag.png" alt=""></h2>
      <h2 v-else-if="details.original_language === 'fr'"><strong>Language:</strong><img src="../assets/Flag_of_France.png" alt=""></h2>
      <h2 v-else-if="details.original_language === 'es'"><strong>Language:</strong><img src="../assets/spainflag.png" alt=""></h2>
      <h2 v-else-if="details.original_language === 'it'"><strong>Language:</strong><img src="../assets/italyflag.png" alt=""></h2>
      <h2><strong>Voto:</strong> {{details.vote_average}}</h2>
      <span><strong>Overview:</strong> {{details.overview}}</span>
  </div>
</template>

<script>


export default {
  name: 'Movie',
  props: {
    details: Object
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
   .movie {
       width: calc((100% / 4) - 40px);
       height: auto;
       background-color: black;
       margin: 20px;

       h1 {
           color: white;
           font-size: 20px;
       }

       h2 {
           color: white;
           font-size: 15px;
           margin: 5px 0;

           img {
               width: 10%;
           }
       }

       span {
           color: white;
           font-size: 10px;
       }
   } 

</style>