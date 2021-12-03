<template>
  <div class="container">
    <div class="background_image">
      <img v-if="details.poster_path !== null" :src="ImgUrlBackground + details.poster_path" alt="">
      <img v-else-if="details.poster_path === null" src="../assets/back_image.png" alt="">
    </div>
    <div class="movie">
      <div v-if="details.backdrop_path !== null"> <img :src="ImgUrl + details.backdrop_path" alt="img"></div>
      <h1><strong>Titolo:</strong> {{details.title}}</h1>
      <h2><strong>Titolo originale:</strong> {{details.original_title}}</h2>
      <h2 v-if="details.original_language === 'en'"><strong>Language:</strong><img src="../assets/englishflag.png" alt="en"></h2>
      <h2 v-else-if="details.original_language === 'fr'"><strong>Language:</strong><img src="../assets/Flag_of_France.png" alt="fr"></h2>
      <h2 v-else-if="details.original_language === 'es'"><strong>Language:</strong><img src="../assets/spainflag.png" alt="es"></h2>
      <h2 v-else-if="details.original_language === 'it'"><strong>Language:</strong><img src="../assets/italyflag.png" alt="it"></h2>
      <h2>
        <strong>Voto:</strong>
        <font-awesome-icon v-for="i in stars()" :key="i" :icon="['fas', 'star']"></font-awesome-icon>
        <!-- <font-awesome-icon v-for="j in 5-stars()" :key="j" :icon="['far', 'star']"></font-awesome-icon> -->
      </h2>
      <span><strong>Overview:</strong> {{details.overview}}</span>
    </div>
  </div>

</template>

<script>
export default {
  name: 'Movie',
  props: {
    details: Object
  },
  data() {
    return {
      ImgUrl: "https://image.tmdb.org/t/p/w185",
      ImgUrlBackground: "https://image.tmdb.org/t/p/w342"
    }
  },
  methods: {
    stars() {
      return Math.ceil((this.details.vote_average) / 2)
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container {
  width: calc((100% / 6) - 10px);
  height: 340px;
  background-color: rgba(0, 0, 0, 0);
  margin: 20px 5px;
  text-align: center;
  cursor: pointer;
  overflow-y: scroll;

  &:hover .movie {
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

  .movie {
    display: none;
    height: 100%;

    h1 {
      color: white;
      font-size: 20px;
    }

    h2 {
      color: white;
      font-size: 15px;
      margin: 5px 0;

      img {
        width: 5%;
      }
    }

    span {
      color: white;
      font-size: 15px;
      padding: 0 5px;
    }
  }
}
</style>