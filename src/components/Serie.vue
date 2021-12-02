<template>
  <div class="serie">
      <h1><strong>Titolo:</strong> {{details2.name}}</h1>
      <h2><strong>Titolo originale:</strong> {{details2.original_name}}</h2>
      <h2 v-if="details2.original_language === 'en'"><strong>Language:</strong><img src="../assets/englishflag.png" alt=""></h2>
      <h2 v-else-if="details2.original_language === 'fr'"><strong>Language:</strong><img src="../assets/Flag_of_France.png" alt=""></h2>
      <h2 v-else-if="details2.original_language === 'es'"><strong>Language:</strong><img src="../assets/spainflag.png" alt=""></h2>
      <h2 v-else-if="details2.original_language === 'it'"><strong>Language:</strong><img src="../assets/italyflag.png" alt=""></h2>
      <h2><strong>Voto:</strong> {{details2.vote_average}}</h2>
      <span><strong>Overview:</strong> {{details2.overview}}</span>
  </div>
</template>

<script>
export default {
  name: 'Serie',
  props: {
    details2: Object
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
   .serie {
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