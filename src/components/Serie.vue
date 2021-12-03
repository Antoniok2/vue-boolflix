<template>
  <div class="serie">
    <h1 class="type_movie">Series</h1>
    <div v-if="details2.backdrop_path !== null"> <img :src="ImgUrl + details2.backdrop_path" alt="img"></div>
    <h1><strong>Titolo:</strong> {{details2.name}}</h1>
    <h2><strong>Titolo originale:</strong> {{details2.original_name}}</h2>
    <h2 v-if="details2.original_language === 'en'"><strong>Language:</strong><img src="../assets/englishflag.png" alt="en"></h2>
    <h2 v-else-if="details2.original_language === 'fr'"><strong>Language:</strong><img src="../assets/Flag_of_France.png" alt="fr"></h2>
    <h2 v-else-if="details2.original_language === 'es'"><strong>Language:</strong><img src="../assets/spainflag.png" alt="es"></h2>
    <h2 v-else-if="details2.original_language === 'it'"><strong>Language:</strong><img src="../assets/italyflag.png" alt="it"></h2>
    <h2>
        <strong>Voto:</strong>
        <font-awesome-icon v-for="i in stars()" :key="i" :icon="['fas', 'star']"></font-awesome-icon>
        <!-- <font-awesome-icon v-for="j in 5-stars()" :key="j" :icon="['far', 'star']"></font-awesome-icon> -->
    </h2>
    <span> {{`Overview: ${details2.overview}`}}</span>
  </div>
</template>

// <font-awesome-icon icon="star"></font-awesome-icon> in questo modo inserisco l'icona di font-awesone

<script>
export default {
  name: 'Serie',
  props: {
    details2: Object
  },
  data() {
    return {
      ImgUrl: "https://image.tmdb.org/t/p/w185",
      voto: []
    }
  },
  methods: {
      stars() {
          return Math.ceil((this.details2.vote_average) / 2)
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
   .serie {
       width: calc((100% / 4) - 40px);
       height: auto;
       background-color: black;
       margin: 20px;

       .type_movie {
           text-align: center;
           margin-bottom: 5px;
       }

       h1 {
           color: white;
           font-size: 20px;
       }

       div {
           text-align: center;
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