<template>
  <div class="container">
    <div class="background_image">
      <img v-if="details2.poster_path !== null" :src="ImgUrlBackground + details2.poster_path" alt="">
      <img v-else-if="details2.poster_path === null" src="../assets/back_image.png" alt="">
    </div>
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
      ImgUrlBackground: "https://image.tmdb.org/t/p/w342"
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
.container {
  width: calc((100% / 5) - 10px);
  height: 340px;
  background-color: rgba(0, 0, 0, 0);
  margin: 20px 5px;

  &:hover .serie {
    display: block !important;
  }

  &:hover .background_image {
    display: none;
  }

  .background_image {
    width: 100%;
    height: 100%;

    img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
  }

  .serie {
    display: none;
    height: 100%;

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

      img {
        width: 20%;
      }
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
} 
</style>